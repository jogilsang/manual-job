# manual-job
직무 면접 및 시험 대비용  

### Android
1. 자바와 코틀린의 차이는?

2. 안드로이드 4대 컴포넌트는?
- 액티비티, 서비스, 브로드 캐스트, 컨텐츠 프로바이더입니다.


### java
1. 클래스와 오브젝트의 차이는 뭐죠?

1. 오버라이드와 오버로드의 차이점?

1. 퀵소트와 버블소트 설명가능?

1. 스택,트리,큐,힙의 개념 설명할수있나요?

1. 가비지 콜렉션에 대해 설명할수있나요?

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

### DB
1. 데이터베이스에서 인덱스에 대해 설명해주세요

### Network
1. OSI 7 Layer에 대해 설명할수있나요?

### C, C++
1. 포인터 설명가능?











