# 정렬 (Sort)

## 버블 정렬 (Bubble Sort)

![bubble-sort-001](https://github.com/SuhyungK/SuhyungK/assets/97926368/4517194d-3dd1-4242-b365-2e15a7c42363)

- 서로 인접한 두 원소를 비교하여 정렬하는 방식
- 시간 복잡도 : O(N^2)
- 최선의 경우 : O(N)
    - 배열이 이미 정렬되어 있는 경우, 교환(swap)이 한 번도 일어나지 않으므로 교환 여부를 판단할 수 있다면 O(N)만에 탐색이 종료될 수 있음
- 공간 복잡도 : O(N)
    - 주어진 배열 내부에서만 교환이 일어나기 때문
- 잘 사용되지 않고, 가장 성능이 좋지 않은 정렬 방식

**동작 원리**
1. 앞에서부터 현재 원소와 바로 다음 원소를 비교한다.
2. 현재 원소가 바로 다음의 원소보다 크다면 교환(swap)한다.
3. 다음 원소 위치로 이동하여 다시 해당 원소와 그 다음 원소를 비교한다.

**구현**
```java
public static void bubbleSort(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
        for (int j = 0; j < arr.length - i - 1; j++) {
            if (arr[j] > arr[j+1]) {
                swap(arr, j, j+1);
            }
        }
    }
}
```

## 선택 정렬 (Selection Sort)

![selection-sort-001](https://github.com/SuhyungK/SuhyungK/assets/97926368/8cbcbc43-dcdd-48b9-9cd0-595836985b03)

- 해당 배열에서 가장 최소값을 선택해 가장 앞에서부터 정렬하는 
- 해당 값을 넣을 위치는 정해져 있고, 어떤 값(최소값)을 넣을지를 선택하는 알고리즘
- 시간 복잡도 : O(N^2)
- 동일한 값에 대해 기존의 순서가 유지되지 않는 *불안정 정렬*

**동작 원리**
1. 주어진 배열에서 최소값을 찾는다.
2. 최소값을 맨 앞 자리의 값과 교환한다.
3. 이미 정렬이 이뤄진 맨 앞 자리의 값을 제외한 나머지 값들로 위의 과정을 반복한다.

**구현**
```java
public static void selectionSort(int[] arr) {
    for (int i = 0; i < arr.length - 1; i++) {
        int minIndex = i;
        for (int j = i+1; j < arr.length; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        swap(arr, i, minIndex);
    }
}
```

## 삽입 정렬 (Insertion Sort)

![insertion-sort-001](https://github.com/SuhyungK/SuhyungK/assets/97926368/7f40731e-90d5-4ae1-a7fc-b554427e9c59)

- 현재 비교하고자 하는 값과 그 이전에 위치한 원소들과 비교하는 정렬 알고리즘  
- 시간 복잡도 : 최악의 경우 O(N^2) / 최선의 경우 O(N)

**동작 원리**  
1. 현재 타겟이 되는 원소와 이전 위치의 원소들을 비교한다. (두 번째 원소부터 시작)
2. 타겟이 되는 원소가 이전 위치의 원소보다 작다면 위치를 서로 교환한다.
3. 다음 위치의 원소를 타겟으로 하여 해당 과정을 반복한다.

```java
public static void insertionSort(int[] arr) {
    for (int i = 1; i < arr.length; i++) {
        
        // 타겟 원소
        int target = arr[i];
        int j = i - 1;

        // 타겟 원소 이전의 값들 중 타겟 원소보다 크거나 같은 값이 나올 때까지 반복
        while (j >= 0 && target < arr[j]) {
            arr[j + 1] = arr[j]; // 이전의 값들을 한 칸씩 뒤로 이동
            j--;
        }

        arr[j + 1] = target; // 타겟 값을 해당 위치에 삽입
    }
}
```

## 힙 정렬 (Heap Sort)

- 완전 이진 트리 기반의 힙 자료구조를 사용한 정렬
- 부모 노드가 자식 노드보다 항상 우선순위가 높다는 조건을 만족시키며 완전 이진 트리 형태를 채워나가는 알고리즘 방식
- 힙을 만드는 과정은 heapify로 부모 노드에서 자식 노드로 진행되기 때문에 sift down 이라고 함
- 전체 정렬보다는 부분 정렬을 할 때 유리
- 시간 복잡도 : O(NlogN)

## 퀵 정렬 (Quick Sort)

## 병합 정렬 (Merge Sort)


