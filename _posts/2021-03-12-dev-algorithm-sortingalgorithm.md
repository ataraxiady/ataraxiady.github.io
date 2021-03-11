---
layout: post
title:  "기본 정렬 알고리즘 요약(선택,버블,삽입,합병,퀵,힙)"
subtitle:   
categories: dev
tags: algorithm
comments: true
header-img: 
---

기본적인 정렬 알고리즘에 대한 요약이다.

[선택 정렬 (Selection sort)](#선택-정렬-selection_sort)  
[버블 정렬 (Bubble sort)](#버블-정렬-bubble-sort)  
[삽입 정렬 (Insertion sort)](#삽입-정렬-insertion-sort)  
[합병 정렬 (Merge sort)](#합병-정렬-merge-sort)  
[퀵 정렬 (Quick sort)](#퀵-정렬-quick-sort)  
[힙 정렬 (Heap sort)](#힙-정렬-heap-sort)  

---

## 선택 정렬 (Selection sort)
- 가장 작은 수를 선택하고 정렬이 되지 않은 부분의 첫번째 인덱스에 위치한 element와 교환하고 이를 반복한다.
- 안정적이지않다
- O(n^2)

```python
# 배열의 처음부터 끝까지 순회한다. 
for i in range(len(A)): 
	
	# 가장 작은 element르 찾는다.
	min_idx = i 
	for j in range(i+1, len(A)): 
		if A[min_idx] > A[j]: 
			min_idx = j 
			
	# 가장 작은 element와 정렬이 되지 않은 부분의 첫번째 인덱스에 위치한 element를 swap 
	A[i], A[min_idx] = A[min_idx], A[i] 
```


## 버블 정렬 (Bubble sort)
- 좌측 값이 본인보다 크면 교환 or 우측 값이 본인보다 작으면 교환
- 이미 정렬이 되어있는 상태라면 __O(n)__, 거꾸로 정렬이 되어있다면 __O(n^2)__

```python
def bubbleSort(arr): 
	n = len(arr) 
 
	for i in range(n): 
        #좌측이 본인보다 크다면 교환
		for j in range(0, n-i-1): 
			if arr[j] > arr[j+1] : 
				arr[j], arr[j+1] = arr[j+1], arr[j] 

```

## 삽입 정렬 (Insertion sort)
<img src="https://ataraxiady.github.io/assets/img/dev/algorithm/insertionsort.png">

- 현재 위치에서 그 아래 인덱스 배열 값들을 비교하여 자신이 들어갈 위치를 찾아 삽입하는 정렬
- Best case: __O(n)__, 이미 오름차름으로 정렬이 되어있는 경우, n-1번 비교 후 swap 없음
- Average case: 랜덤으로 나열되어있는 경우
- Worst case:  __O(n^2)__, 내림차순으로 정렬 되어있는 경우, 최대로 비교하게 된다

```python
def insertionSort(arr):
	# index=1부터 끝까지 순회
	for i in range(1, len(arr)):

		key = arr[i]

		# 비교 후 swap
		j = i-1
		while j >= 0 and key < arr[j] :
				arr[j + 1] = arr[j]
				j -= 1
		arr[j + 1] = key
```

## 합병 정렬 (Merge sort)
<img src="https://ataraxiady.github.io/assets/img/dev/algorithm/mergesort.png">

- Divide & Conquer 알고리즘
- Divde : 배열을 n/2로 나눈다 (재귀를 통하여 데이터 사이즈가 1일 때(싱글톤 element) 까지, log2(N)번에 걸쳐 나눔)
- Conquer : 두 조각을 정렬한다 
- Combine : 정렬된 두 리스트를 하나로 합친다
- 시간복잡도: O(nlogn)
- 단점 : 메모리차지가 크다

```python
def mergeSort(arr):
	if len(arr) > 1:
		# 배열의 중간찾기
		mid = len(arr)//2
		# 배열 중간의 왼쪽
		L = arr[:mid]
		# 배열 중간의 오른쪽
		R = arr[mid:]
		# 재귀를 통해 계속 이등분한다
		mergeSort(L)
		mergeSort(R)
		i = j = k = 0
		# Copy data to temp arrays L[] and R[]
		while i < len(L) and j < len(R):
			if L[i] < R[j]:
				arr[k] = L[i]
				i += 1
			else:
				arr[k] = R[j]
				j += 1
			k += 1
		# Checking if any element was left
		while i < len(L):
			arr[k] = L[i]
			i += 1
			k += 1
		while j < len(R):
			arr[k] = R[j]
			j += 1
			k += 1
```
## 퀵 정렬 (Quick sort)
<img src="https://ataraxiady.github.io/assets/img/dev/algorithm/quicksort.png">

- Divide & Conquer 알고리즘이지만 합병정렬과 다르게 반으로 나뉘어지지않고 __피벗__ 을 기준으로 나눈다.
- 일반적으로 가장 첫번째 element을 피벗으로 정한다
- 이상적인 상황에서는 __O(nlog2(n))__, unbalanced한 상황에서는 __O(n^2)__
- 항상 빠르지 않고 재귀를 사용하기에 저장을 위한 extra space가 필요하다

```python
def partition(arr, low, high): 
	i = (low-1)		 # 가장 작은 엘리먼트의 인덱스
	pivot = arr[high]	 # 이 코드에서의 피벗은 가장 마지막 element이다.

	for j in range(low, high): 

		# If current element is smaller than or 
		# equal to pivot 
		if arr[j] <= pivot: 

			# increment index of smaller element 
			i = i+1
			arr[i], arr[j] = arr[j], arr[i] 

	arr[i+1], arr[high] = arr[high], arr[i+1] 
	return (i+1) 

# arr[] --> Array to be sorted, 
# low --> Starting index, 
# high --> Ending index 

def quickSort(arr, low, high): 
	if len(arr) == 1: 
		return arr 
	if low < high: 

		# pi is partitioning index, arr[p] is now 
		# at right place 
		pi = partition(arr, low, high) 

		# Separately sort elements before 
		# partition and after partition 
		quickSort(arr, low, pi-1) 
		quickSort(arr, pi+1, high) 
```

## 힙 정렬 (Heap sort)
- 내림차순 정렬을 위해서는 max heap(부모가 자식보다 클 것), 오름차순 정렬을 위해서는 min heap(부모가 자식보다 작을 것)을 구성한다.
- heapify란 힙의 성질을 만족시키도록 노드들이 위치를 조정하는 과정을 말한다.
- max heap의 삽입 : 삽입되는 새로운 노드를 힙의 마지막 노드에 삽입한다. 그 후 부모노드들과 비교 후 교환하여 max heap의 성질을 만족시킨다.
- max heap의 삭제 : 루트 노드를 삭제(라기보단 다른 곳에 저장해두고) 후 가장 right-bottom노드를 루트로 설정한 한 후 하나하나 비교하여 max heap의 성질을 만족시키도록 트리를 재조정한다.
- 메모리를 사용할 필요가 없어 시간복잡도가 __O(nlog2(n))__ 로 좋은 편이다
- 전체 자료 정렬이 아닌 가장 큰 값 몇개만 필요할 때 가장 유용하다.

```python
# To heapify subtree rooted at index i.
# n is size of heap
def heapify(arr, n, i):
	largest = i # Initialize largest as root
	l = 2 * i + 1	 # left = 2*i + 1
	r = 2 * i + 2	 # right = 2*i + 2

	# See if left child of root exists and is
	# greater than root
	if l < n and arr[largest] < arr[l]:
		largest = l

	# See if right child of root exists and is
	# greater than root
	if r < n and arr[largest] < arr[r]:
		largest = r

	# Change root, if needed
	if largest != i:
		arr[i], arr[largest] = arr[largest], arr[i] # swap

		# Heapify the root.
		heapify(arr, n, largest)

# The main function to sort an array of given size
def heapSort(arr):
	n = len(arr)
	# Build a maxheap.
	for i in range(n//2 - 1, -1, -1):
		heapify(arr, n, i)

	# One by one extract elements
	for i in range(n-1, 0, -1):
		arr[i], arr[0] = arr[0], arr[i] # swap
		heapify(arr, i, 0)
```




<출처>geeksforgeeks