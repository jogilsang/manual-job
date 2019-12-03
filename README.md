# manual-job
직무 면접 및 시험 대비용  

### Android
1. Java와 Kotiln의 차이는?

2. Android 4대 Component는?
```
액티비티, 서비스, 브로드 캐스트, 컨텐츠 프로바이더입니다.
```

3. PendingIntent 란?
```
인탠트를 다른 클래스에서 실행시켜줄수있게 위임해주는 클래스입니다.
보통 Notification Alarm과 상호작용할떄, 사용됩니다.
또한 startActivity, startService, sendBroadCast 메소드를 호출할때 인탠트를 팬딩인탠트에 담아서 사용합니다.
```

4. Http Library에는 어떤게있을가요?
```
HttpUrlConnection, Volley, OKHttp, Retrofit 이 있습니다.
```

5. Android의 MemoryStructure는?
```
렘, 내장메모리, 외장메모리가 있습니다.
렘은 프로그램이 실행될때 차지하는 공간으로, 런타임시 프로그램이 상주하게됩니다.
```

6. RestfulAPI에 대해 설명하시오
```
웹상에 존재하는 자원을 URI형태로 사용하는 방법입니다.
HTTP표준구조로 사용가능하며, http 캐싱을 활용할수있는 장점이있습니다.
어떤 요청인지 URI를 보고, 확인할수있습니다. 따라서 직관적입니다
서버와 클라이언트를 구분해서 명확하게 개발이 가능합니다.
```

7. RxJava 는 무엇인가요?
```
반응형 프로그래밍의 한 종류로, 비동기로 데이터를 효율적으로 처리할수있습니다.
```

8. React Programming은 무엇인가요?
```
반응형 프로그래밍의 경우 명령형이 아닌 선언형을 사용합니다. 
함수를 호출이 아닌 인자로 사용할수있어, 다양한 함수형 도구를 다룰줄 알아야합니다
예시로 RxJava가 있습니다.
```

9. WebView는 무엇인가요?
```
안드로이드 프레임워크에 내장된 뷰 컴포넌트입니다.
웹페이지를 보거나, HTML을 볼수있게 할수있어 하이브리드앱에서 자주 사용됩니다.
```

10. Android의 Memory 관리방식에 대해 설명해보세요
```
프로세스가 누적되면, 메모리가 부족해지게됩니다.
프로세스의 사용빈도, 우선순위에 따라 메모리 확보를 위해 제거됩니다.
프로세스가 누적되는 이유는, 앱이 실행되면서 액티비티, 서비스 등이 앱 프로세스를 발생시킵니다.
재실행하는것보다 다시 생성하는게 딜레이가 크기때문에, 사용자가 다시 실행할걸 대비해서 앱 프로세스를 종료하지않습니다.
```

11. Application에 대해 설명해보세요
```
어플리케이션은 앱 프로세스가 실행되면 제일 먼저 생성되는 객체입니다.
따라서 앱 프로세스와 동일시 할수있습니다. 앱이 백그라운드에서 실행되도, 앱 프로세스가 죽지않기때문에
어플리케이션 객체 역시 살아있습니다.
```

12. Context에 대해 설명해보세요.


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











