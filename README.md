# manual-job
Job interviews and exam preparation  

### Android
1. Java와 Kotiln의 차이는?

2. Android 4대 Component는?
```
액티비티, 서비스, 브로드 캐스트, 컨텐츠 프로바이더입니다.
액티비티는 화면관리와 사용자 이벤트 처리에 사용됩니다.
서비스는 특정한 기능을 백그라운드에서 처리합니다.
브로드캐스트 리시버는 안드로이드에서 발생하는 특정 메세지를 처리하기 위한 컴포넌트입니다.
콘텐츠 프로바이더는 앱 사이의 데이터 공유를 위한 인터페이스를 제공하는 컴포넌트입니다.
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
```
액티비티, 리시버, 서비스, 브로드캐스트 등의 컴포넌트들이 동작시 필요한 정보를 가지고있는 객체입니다.
각 컴포넌트들은 생성시 자신만의 Context 객체를 생성하게됩니다.
컨텍스트에는 LayoutInflater 등 시스템 서비스와 패키지명 등의 앱정보가 담겨있습니다. 
```

13. 서비스에 대해 설명해보세요.
```
서비스는 백그라운드에서 동작하는 컴포넌트입니다.
사용자가 눈으로 볼수없고, 정해진 시간동안 동작하지않습니다.
서비스는 Service클래스를 상속받아, OnBind와 onStartCommand를 오버라이드 하여 사용합니다
사용전 Manifest 파일에 Service 태그를 선언합니다.
1개의 단말당 하나의 서비스를 동작할수있으며, 메인스레드에서 보통 사용됩니다.
대기상태 등을 필요로 할때 별도의 쓰레드를 이용해서 동작합니다.
StartService나 bindService 메소드를 통해 실행합니다.
```

14. 액티비티 간에 임의의 클래스 객체를 전달하지 못하는 이유는 무엇이고, 전달하기위해 어떡해야하는가?
```
액티비티간에 데이터는 인탠트를 이용해서 전달합니다. 인탠트의 경우 기본 data형 타입으로 보낼수있습니다.
그 이유는 앱 프로세스와 매니저 프로세스 간의 프로세스 통신이기때문에, 객체주소가 아닌 값을 복사해서 전달하는 형태이기때문입니다.
따라서 임의의 클래스 객체를 전달하기위해선, Serialiable 또는 Parcerble 인터페이스를 구현하여 객체를 직렬화 해서 전달해야합니다.
```

15. 안드로이드 애플리케이션 만들 때 중요한 파일과 폴더에 대한 설명해보세요
```
src 폴더가 있습니다. 패키지이름으로 사용할수있고, java나 kotlin 등의 파일이 포함됩니다.
res 폴더가 있습니다. drawable, layout 등 모든 리소스파일을 담고있습니다.
assets 폴더가 있습니다. html이나 db파일을 넣어놓을수있습니다.
gen 폴더가있습니다. R.java와 같이 리소스를 참조하는 파일들이 있습니다.
bin 폴더가있습니다. 빌드과정에서 ADT에 의해 생성된 apk파일이있습니다. apk는 애플리케이션 바이너리 파일입니다.
```

16. Extent Intent(명시적 인탠트)와 Implicit Intent(암시적 인탠트)의 차이는?
```
호출대상의 정의여부입니다.
암시적 인탠트는 action, data, type 등을 정의해줘야합니다.
```

17. SharedPreferences에 대해 설명해보시겠어요?
```
안드로이드의 가장 기본적으로 사용할수있는 저장테크닉입니다.
key-value 쌍의 형태로 xml파일로 저장하게되는대, 기본데이터형 value만 허용합니다.
```

18. 안드로이드의 서비스 3가지 모드에 대해 설명해보시겠어요
```
START_STICKY : 서비스 강제종료시, 시스템이 서비스를 다시 시작시켜준다. 대신 인탠트는 null이다.
START_NOT_STICKY : 서비스가 강제종료되면 다시 시작하지않는다.
START_REDELIVER_INTENT : 서비스 강제종료시, 시스템이 서비스를 다시 시작시켜주는대 인탠트도 그대로이다.
```
19. 서비스와 쓰레드의 차이는 무엇인가요?
```
서비스는 UI없이 백그라운드에서 오랜시간 작업처리가 가능한 컴포넌트이다.
쓰레드는 백그라운드에서 몇몇 작업수행을 위한 O.S레벨 기능이다.
```

20. 프래그먼트와 액티비티는 어떤 차이가있나요?
```
독립적으로 존재할수있느냐의 유무가있습니다.
프래그먼트는 액티비티에 종속되기때문에, 독립적으로 사용될수없습니다.
하나의 액티비티는 여러개의 프래그먼트를 포함할수있고, 하나의 프레그먼트는 여러 액티비티에서 재사용될수있습니다.
```

21. Bundle은 무엇인가요?
```
인탠트 간에 데이터를 전달하는 holder입니다.
액티비티의 UI 등 상태정보를 가지고있어 복원할떄 oncreate에 전달되어 사용됩니다.
메모리 부족이나 회전시 사용됩니다.
onSaveInstanceState() : onPause() 이전 또는 이후에 호출된다.
onRestoreInstanceState() : onStart() 이후에 호출된다.
```

22. ANR이란?
```
메인스레드에서 수행되는 작업이 무거워지면, 프로세스가 멈추는걸 애기합니다.
유저가 액티비티를 터치했는대도 5초이상 반응이 없는경우에도 ANR이 동작한다.
```

23. this랑 getApplicationContext의 차이는?
```
this는 항상 현재 클래스의 객체를 가리킵니다. app context는 전체 프로세스를 가리킵니다.
app context는 하나만 존재하므로 앱이 동작하는동안 컨트롤하려면 app context를 사용하고 그 외에는 this를 사용합니다.
```




### java
1. 클래스와 오브젝트의 차이는 뭐죠?
```
```

2. 오버라이드와 오버로드의 차이점?
```
오버라이딩은 부모클래스의 메소드를 자식클래스에서 재정의해서 사용하는것입니다.
오버로딩은 메소드 이름은 같지만 서로 다른 인자의 개수, 인자의 데이터형이 다른 것을 뜻합니다.
```

3. 가비지 콜렉션에 대해 설명할수있나요?
```
```

4. final 키워드에 대해 설명해보실래요
```
변수, 메소드, 클래스 각각에서 다르게 작용합니다
변수에 final 키워드가 사용되는경우, 변수의 값은 초기화된 이후 변경이 불가능합니다.
메소드에 final 키워드가 사용된경우, 하위클래스에서 오버라이드 할 수 없습니다
클래스에 final 키워드가 사용되는경우, 하위클래스가 상속할수없습니다.
```

5. finally 키워드
```
try/catch 블록과 함께사용되며, 예외유무와 관계없이 원래의 제어흐름으로 돌아가기전 
무조건 실행됩니다
```

6. finalize 메서드
```
가비지 컬렉터가 객체를 삭제하기전에 호출하는 메소드입니다.
객체가 삭제되기전 실행되어야할 동작이 있다면, 오버라이드하여 정의가능합니다.
```

7. 자바의 컬렉션 프레임워크에는 어떤게 있나요?
```
ArrayList, Vector, LinkedList, HashMap 등이 있습니다.
```

8. 생성자를 private으로 하면 계승 관점에서 어떤 영향을 주게되나?
```
외부에서 해당 클래스의 객체를 생성할수없다
따라서 클래스 내에서 public 메소드로 객체를 생성해서 제공해줘야한다
```

9. java의 finally 블록은 try-catch-finally의 try 블록안에 return문을 넣어도 실행되나?
```
finally는 try 블록안에 continue, break, return 등이 있어도 무조건 수행된다
수행되지않는경우는 가상머신이나 쓰레드가 죽는경우이다.
```

10. final, finally, finalize의 차이는?
```
final은 변수와 메소드, 클래스에 적용된다
finally는 try-catch 블록이 끝나면, 이전 흐름으로 돌아가기전에 실행되는 키워드
finalize는 가비지 컬렉터가 더 이상 참조를 하지않는 객체를 메모리에서 삭제하기전
호출하는 메소드. 삭제 전 동작을 정의할때 오버라이드 해서 사용할수있다.
```

11. C++ 템플릿과 java의 제네릭의 차이를 설명하라
```
java의 제네릭에는 int같은 원시형type은 들어갈수없지만, C++은 들어갈수가있습니다.
```

12. java의 객체 리플렉션에 대해 설명하고 유용한 이유를 밝혀라
```
프로그램이 어ᄄᅠᇂ게 동작하는지 정보를 실행 시간에 관측하고 조정할수있고,
메소드,필드 등을 직접 접근할수있기때문에 디버깅하거나 테스트할떄 유용.
```

13. 자바에서 쓰레드를 구현하는 방법은 어떤게 있나요?
```
Thread 클래스를 상속받는 것과 Runnable 인터페이스를 구현하는 것입니다
```

14. Thread 클래스를 상속받는것과 Runnable 인터페이스를 구현하는 것중 어떤게 나을까요?
```
자바는 다중상속을 지원하지않기때문에, 다른 클래스를 상속받고자 한다면
Runnable 인터페이스를 구현하는게 좋습니다
Thread 클래스의 모든 걸 상속받으면 효율이 떨어지기때문에, 필요한 부분만 Runnable을 통해 구현하는게 좋습니다.
```

15. Synchronized와 lock은 키워드는 무엇인가요?
```
하나의 프로세스에서 서로 다른 쓰레드가 동작하는경우, 메모리를 공유합니다.
메모리를 공유한다는건, 같은 자원에 동시에 접근할수있다는 뜻입니다.
이러한 쓰레드들의 공유자원 접근제어에 대해서 동기화 방법을 지원하는 키워드입니다.
즉 서로 다른 스레드가 적절히 동기화 되도록 하는 수단을 제공합니다.
```

16. 쓰레드와 프로세스의 차이는?
```
프로세스는 실행되고있는 프로그램 개체이다.
쓰레드는 프로세스 안에 존재하며, 프로세스의 자원을 공유한다.
각각의 쓰레드는 별도의 레지스터와 스택을 가지고있지만, 힙 메모리는 서로 읽고 쓸수있다.
```

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

### SW (Software)
1. 폭포수 개발론에 대해 설명해보세요  
```
폭포수 모델은 순차적인 소프트웨어 개발 프로세스입니다.
요구사항 확인, 설계, 구현, 시험, 설치, 유지보수와같은 단계로 수행됩니다.
전 단계가 수행되어 완료되기 전에는 다음단계로 진행할 수 없도록 제한합니다.
```

2. 애자일 개발론에 대해 설명해보세요.  
```
```
3. 소프트웨어 라이센스에 대해 설명해보세요.  
```
MIT License
Apache Lisence

```

4. 세마포어와 뮤텍스에 대해 설명해보세요
```

```

5. 교착상태는 언제 발생하나요?
```
프로세스들이 자원을 점유한상태에서 계속 요구하는경우
서로 점유하고있는 자원을 서로 요구하는 경우
자원을 한번에 하나의 프로세스만 사용할수있는경우
```

6. 가상기억장치는 뭔가요?
```
보조기억장치를 주기억장치 처럼 사용하는것입니다.
```

7. 가상기억장치는 어떡해만드나요?
```
페이징 기법과 세그멘테이션 기법 두가지가있습니다.
```

8. 페이징 기법과 세그멘테이션 기법은 무엇인가요?
```
```

9. 레지스터는 뭔가요?
```
CPU의 임시기억장소입니다.
```

10. 버스는 무엇인가요?
```
CPU와 메모리간에 정보 교환을 위한 전송선으로 브릿지 역활을 수행합니다.
```

11. 컴퓨터는 무엇으로 구성되있나요?
```
중앙처리장치인 CPU와 주기억장치, 제어장치, 연산장치 그리고 입력장치,출력장치,보조기억장치가 있습니다.
```

12. 저장장치의 성능은 어떡해 표현될가요?
```
저장용량, 접근 및 저장속도, 내구성,저장대역폭, 코스트 등이 있습니다.
```

13. 병렬시스템의 장점은?
```
기억장치 공유가 가능합니다. 일부 오류가 생겨도 전체에 지장없습니다.
```

14. 운영체제란?
```
```

15. 응집도와 결합도의 관계?
```
모듈은 높은 응집도와 낮은 결합도를 가져야합니다.
모듈 내부에서는 강한 응집력을, 다른 객체간에는 연관성의 복잡도가 떨어질수록 좋습니다.
```

16. 추상화란 무엇인가요?
```
필수적이 아닌 세부적인 것을 생략해준다.
데이터,컨트롤,과정 세 가지를 추상화할수있습니다.
```

17. 정보은닉
```
모듈의 내용을 감추고, 인터페이스를 통해서만 메세지는 전달하는 개념입니다.
```

18. 모듈화
```
크고 복잡한 문제를 작은 단위인 모듈로 분할하여 문제를 정복할수있다.
시스템 유지보수를 용이하게한다.
```

19. 캡슐화
```
정보은닉을 통해 추상화,독립성을 얻는것입니다.
```

20. 상속은 무엇인가요?
```
여러 클래스의 공통된 속성 등을 일반화시켜서, 다른 클래스가 정보를 받을수있게 하는것입니다.
```

21. 다형성은 무엇인가요?
```
하나의 함수이름이나 연산자가 여러 목적으로 사용될수 있는것입니다.
상위클래스의 메소드를 하위클래스가 오버라이딩하는 것을 예로들수있습니다.
```

22. 객체지향설계를 해보세요
```
1. 모호성의 해소 : 누가 그것을 어떻게 사용할것인지?
2. 핵심 객체의 설계
3. 관계 분석 : 객체 간에 상속을 받아야하는지? 다대다인지, 다대일인지?
4. 행위 분석 : 객체가 행해야 하는일들은 뭐고, 어떡해 상호작용할것인가?
```

23. 객체지향은 어떤 원칙을 가져야하나요?
```
하나의 클래스가 하나의 method를 가지게된다
직접적인 수정보다는 상속을 통해 개선을 요구
하위클래스는 상위클래스를 참조할수있어야한다.
사용자별로 다른 인터페이스 제공
인터페이스를 통한 추상화로 변경가능성을 최소화
```

24. 디자인패턴(싱글톤)에 대해 설명해보세요
```
특정 클래스의 인스턴스가 오직 하나임을 보장한다.
```

25. 디자인패턴(팩토리 메서드)에 대해 설명해보세요
```
원하는 시점에 인스턴스를 생성할수있도록, 하위 클래스로 책임을 미루는 것
```

### DB
1. 데이터베이스에서 인덱스에 대해 설명해주세요  

2. 트랜젝션의 특징에 대해 설명해보세요  

### Network
1. OSI 7 Layer에 대해 설명할수있나요?

### C, C++
1. 포인터 설명가능?












