
## RxJava
### 목차
1. [ReactiveX란 무엇인가](#p1)
2. [마블다이어그램이란](#p2)
3. [just Method란](#p3)
4. [Reactive Streams란](#p4)
5. [Cold Publisher & Hot Publisher란](#p5)
6. [변환연산자 concatMap과 flatMap의 차이점은?](#p6)
7. [변환연산자 switchMap과 concatMap의 차이점은?](#p7)
8. [변환연산자 flatMap 의 동작유형은?](#p8)

---

## 1. ReactiveX란 무엇인가
### p1
```
변화의 전파와 데이터의 흐름과 관련된 선언적 프로그래밍이다.
변화의 전파와 데이터의 흐름이란, 데이터가 변경되면, 이벤트가 발생하고, 데이터를 전달한다.
선언적 프로그래밍은 동작을 명시하는 명령형 프로그래밍과 달리, 목표를 선언하는 프로그래밍이다.
데이터를 발행하고, 데이터를 가공하고, 데이터를 구독해서 처리하는 구조이다.
```

---

## 2. 마블다이어그램이란
### p2
```
비동기적인 데이터의 흐름을 시간의 흐름에 따라 시각적으로 표시한 다이어그램이다.
타임라인은 왼쪽에서 오른쪽으로 시간이 흐르며, 시간순으로 데이터가 발행된다.
IDE에서 ctrl + q를 통해 다이어그램 관찰가능하다.
```

---

## 3. just method란
### p3
```
Observable과 Flowable을 생성하는 함수이다
Flowable는 Reactive Streams Interface를
구현했으며, Observable는 Reactive Streams Interface를 구현하지않는다
```

---

## 4. Reactive Streams란
### p4
```
리액티브 프로그래밍의 표준 라이브러리이다.
GIT주소로 Reactive-streams-jvm이있다.
publisher와 subscriber, Processor의 개념이있다.
```

---

## 5. Cold Publisher & Hot Publisher란
### p5
```
Cold Publisher는 Subscriber가 Subscribe 할 때마다 데이터를 처음부터 noti한다.
특정시점 이전의 Subscriber와 이후 Subscriber가 차이가 없다
Cold publisher는 TImeline이 하나이다.

Hot Publisher는 subscriber가 subscribe 한 시점부터 data를 noti 받는다.
subscribe 이전시점의 data는 noti 받을 수 없다.
특정시점 이전의 Subscriber와 이후 Subscriber가 차이가 있다.
Hot Publisher는 TimeLine이 여러개이다.
```
---

## 6. 변환연산자 concatMap과 flatMap의 차이점은?
### p6
```
concatMap은 순서를 보장하지만, 속도가 느리다
concatMap은 반환된 Observable을 하나씩 순서대로 실행한다.
flatMap은 순서를 보장하지않지만, 속도가 빠르다.
```

---
## 7. 변환연산자 switchMap과 concatMap의 차이점은?
### p7
```
concatMap과 switchMap 둘다 순서를 보장한다.
하지만 switchMap은 새로운 데이터가 통지되면, 기존에 진행되던 작업이 중단된다.
예를들면 모든 것에 대한 질의를 가져오는 것이아니라, 이전에 진행되던 질의는 중단한다.
따라서 concatMap보다는 빠르다.
```
---

## 8. 변환연산자 flatMap 의 동작유형은?
### p8
```
첫번째는 한개의 데이터를 받아서 여러개로 변환하는 것이다.
두번째는 원본 데이터와 변환된 데이터를 조합해서 새로운 데이터를 통지한다.
새로운 Observable을 생성할 수 있기때문이다.
```
---

## Reference
[Kevin의 알기 쉬운 RxJava 1부](https://www.inflearn.com/course/%EC%9E%90%EB%B0%94-%EB%A6%AC%EC%95%A1%ED%8B%B0%EB%B8%8C%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-1/dashboard)