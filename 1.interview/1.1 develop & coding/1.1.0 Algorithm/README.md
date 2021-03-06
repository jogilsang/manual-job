
### Algorithm & Data Structure
1. 선택정렬을 설명하고, 코드로 구현해보세요
```java
public static void selectionSort(int[] arr, int start) {

   if(start < arr.length - 1) {
      int min_index = 0;
      for(int i = start ; i < arr.length  ; i++) {
          if(arr[i] < arr[min_index]) {
             min_index = i;
          }
      }
      swap(arr, start, min_index);
      selectionSort(arr, start + 1);
   }

}

```

2. 버블정렬을 설명하고, 코드로 구현해보세요.
```java
public static void bubbleSort(int[] arr, int last) {

if(last > 0) {
   for (int i = 1 ; i <= last ; i++) {
       if(arr[i-1] > arr[i]) {
            swap (arr, i-1, i);
       }
   }
   bubbleSort(arr, last -1);
}

}
```

3. 이진트리와 종류에 대해 설명해보세요
```
Binary tree는 child가 최대 2개까지 생성가능한 트리입니다.
Completed Binary tree, Full binary tree, Perfect Binary Tree 세 종류가 있습니다.
Completed Binary tree는 이진트리의 마지막 레벨이 왼쪽부터 차례대로 체워지는경우입니다.
Full binary tree는 child가 2개이거나, 아예없거나 둘중의 하나인경우 tree입니다.
Perfect Binary Tree는 피라미드형 구조로, 노드는 레벨을 n이라고 했을때 2^n-1개 가지고있는 트리입니다.
```

4. 이진검색트리를 설명하고, 구현해보세요
```java
노드를 기준으로 값이 나뉘어져있습니다.
왼쪽 child는 부모보다 값이 작고, 오른쪽 child는 부모노드보다 값이 큽니다.
```

5. 탐욕알고리즘은 무엇인가요?
```
탐욕 알고리즘이란 현재 상황에서 여러가지 경우가 있을 경우, 그 순간의 최선의 선택을 하는 알고리즘입니다.
순간순간 최선을 다해서 선택하다보면, 최종적으로 답을 도출하지만 최선의 답을 보장하진않습니다.

출처: https://makefortune2.tistory.com/26 [Simple in Complex with Simple]
```

6. 다익스트라 알고리즘에 대해 설명해보세요
```
다익스트라 알고리즘은 최단경로를 찾는 대표적인 알고리즘입니다.
기본원리는 하나의 정점에서 다른 모든 정점들의 최단거리를 구합니다.
```

7. 다익스트라 알고리즘의 단점을 애기해보세요
```
다익스트라 알고리즘은 정점을 지날수록 가중치가 증가하는걸 전제로합니다.
따라서 음의 가중치가 있는경우 전제가 무너지기떄문에, 계산할수없습니다.
```

8. 자료구조란 무엇인가요?
```
자료의 특성에 따라 체계적으로 구분한것입니다.
```

9. 자료구조의 종류는 무엇이있나요?
```
선형구조와 비선형구조로 나뉩니다.
선형구조는 자료가 일렬로 되어있으며, 비선형구조는 계층이나 망구조로 되어있습니다.
```

10. 비선형구조에는 뭐가있나요?
```
트리와 그래프가있습니다.
```

11. 자료구조를 선택하는 기준은요?
```
자료의 크기와 자료를 추가,검색,갱신 등 처리하는 시간을 들수있습니다.
```

12. 스택은 어디에쓰이나요?
```
에디터의 Undo 되돌리기 기능, 인터럽트 처리
```

13. 큐는 어디에쓰이나요?
```
작업스케줄링에 사용됩니다.
```

14. 알고리즘이란?
```
문제를 해결하기위한 절차를 기술한것
```

15. 알고리즘에 꼭 필요한건 뭐라고생각하나요?
```
입력과 출력이 필요합니다.
예외처리를 두어야합니다. 
무한히 동작하면 안되기떄문에 종료조건이 필요합니다.
```

16. 실행시간 함수 순서를 애기해볼래요?
```
logn이 제일 작습니다. 그 다음 n, nlogn, n^2, n^3, 2^n 입니다.
```

17. 비선형구조인 트리는 어디쓰이나요?
```
탐색이나 정렬문제에 쓰입니다.
```

18. 비선형구조인 그래프는 어디쓰이나요?
```
컴퓨터 네트워크에 쓰입니다.
```

19. 선형구조에는 뭐가있나요?
```
배열, 리스트, 큐, 스택이있습니다.
```

20. 내부정렬에는 어떤 종류가있나요?
```
버블정렬, 삽입정렬, 선택정렬, 퀵정렬, 병합정렬 (히프정렬,버킷정렬)이있습니다.
```

21. nlogn으로 동작하는 정렬은 무엇이있나요?
```
퀵정렬과 머지정렬, 힙정렬이있습니다.
```

22. 동적계획법은 무엇인가요?
```
동적계획법은 다이나믹 프로그래밍이라고도 표기한다.
답을 구하기 위해서 했던 계산을 계속 반복해야할때, 과거의 구했던 해를 활용하는 방법이다.
한번 계산했던 결과를 메모리에 넣어두는것을 메모이제이션이라고 한다.
```
23. 산술 우측 쉬프트 (ArithMeticRightShift)
```
전체가 오른쪽으로 이동하지만, 왼쪽부호 값은 보존된다.
반복 시, 음수인경우 -1로 수렴
반복 시, 양수인경우 0으로 수렴
```

24. 논리 우측 쉬프트 (logicalRightShift)
```
전체가 오른쪽으로 이동한다. 왼쪽부호 값은 보존되지않으며, 0이 체워진다.
반복 시, 음수이던 양수던 0으로 수렴한다.
```

25. 비트 확인하기 
```java
int getBit(int num, int i) {

if( num & (i << 1) !=0 ) {
  return 1;
}else {
  return 0;
}

}

```

26. 비트 채우기 (1)
```java
int setBit(int num, int i) {
    // 1 << i = 000010000
    // OR연산 : i번째 비트가 1이면 해당 숫자는 바뀌고, 그 외 숫자는 기존값과 동일
    return num | ( 1 << i );
}
```

27. 비트 지우기 (0)
```java
int clearBit(int num, int i) {
   // ~(1 << i) = 1111101111111
   // AND연산 : i번째 비트가 0이면 해당 숫자는 0이되고, 그 외 숫자는 기존값과 동일 
   return num & (~(1 << i));
}