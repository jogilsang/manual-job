## Network
### 목차
1. [OSI 7 Layer란 무엇인가?](#p1)
2. [Web이란 무엇인가?](#p2)
3. [Web서버와 WAS의 종류와 특징은?](#p3)
4. [WAS의 정의와 Web서버와의 차이는?](#p4)
5. [각 OSI Layer 계층별 특징은?](#p5)
6. [서버의 응답값?](#p6)
7. [Connection Pool](#p7)
8. [TIME_WAIT와 TCP_Slow_start](#p8)
9. [http1.0과 http1.1에서의 keep-alive 사용법](#p9)
10. [Latency와 bandwidth란? 그리고 웹 성능을 높이려면?](#p10)
11. [Loadbalancer의 분배방식과 특징은?](#p11)
12. [Sticky Session과 Session Clustering의 의미와 차이는?](#p12)

---

## 1. OSI 7 Layer란 무엇인가?
#### p1
```
웹이란 인터넷을 기반으로 한 서비스이며,
인터넷은 전 세계 컴퓨터를 계증구조로 연결한것이다.
OSI7 Layer는 Layerd architecture로 만들어진 거대한 네트워크 소프트웨어이다.
최근에는 TCP/IP update 모델이 쓰인다.
```

---

## 2. Web서버란 무엇인가?
#### p2
```
Web Server는 html, css, image 등 정적인 데이터를 클라이언트에게 제공하는 서버이다.
```

---

## 3. Web서버와 WAS의 종류와 특징은?
#### p3
```
Web server에는 Apache, IIS, nginx가 있다.
WAS는 IBM, jeus, Tomcat 등이 있다.
```

---

## 4. WAS의 정의와 Web서버와의 차이는?
#### p4
```
WAS는 Web Application Server의 줄임말이다.
php, jsp, asp 등을 통해 동적인 페이지 생성가능 서버이다.
Web서버와는 달리 프로그램 실행환경과 DB접속기능 포함한다.
따라서 WAS는 웹 애플리케이션을 실행시켜 필요한 기능을 수행하고, 그 결과를 웹서버에게 전달하는 미들웨어이다.

WAS는 웹서버와 웹 컨테이너가 결합된것으로, Web서버가 정적컨텐츠가 아니라 동적콘텐츠를 요청받으면 Web Container로 전달한다.
따라서 WAS는 상황에 따라 변하는 정보를 제공할 수 있다.
```

---

## 5. 각 OSI Layer 계층별 특징은?
#### p5
```
물리계층
인코딩이란 0,1의 데이터 나열을 전송하기위해 아날로그 신호로 변환하는 것이다.
디코딩이란 받은 아날로그 신호를 0,1의 데이터 나열로 해석하는 것이다.
물리적으로 연결된 2대의 컴퓨터가 0과 1의 나열을 인코딩과 디코딩 과정을 통해 주고받을 수 있게해주는 모듈이다.
물리적으로 PHY칩으로 구현되있다.

데이터링크 계층
동일 네트워크 구간에서 여러 대의 컴퓨터들이 데이터를 주고받을 수 있는 모듈이다.
시작과 끝에 플래그를 붙여서 데이터를 주고받는다.
물리적으로 랜카드로 구현되있다.

네트워크 계층
여러 네트워크가 연결된 구간에서, IP주소를 이용해서(Routing) 경로를 찾고, 다음 라우터에게 데이터를 넘겨주는것(Forwarding)이다.

전송계층
목적지에 도착 후, 프로세스를 구분할 수 있도록 포트가 할당되서 전송된다.

Application 계층
TCP/TP 프로그래밍을 통해 사용자가 생성할 수 있다.
```

---

## 6. 서버의 응답값은 ?
#### p6
```
1xx: Informational - Request received, continuing process
정보 - 요청을 받음, 계속 진행
2xx: Success - The action was successfully received, understood, and accepted
성공 - 서버가 요청을 성공적으로 처리했음
3xx: Redirection - Further action must be taken in order to complete the request
리다이렉션 - 요청이 완수되기 위해서 추가적인 동작이 이뤄져야 함
4xx: Client Error - The request contains bad syntax or cannot be fulfilled
클라이언트 에러 - 요청에 잘못된 문법이 포함되었거나 제대로 만족시키지 못함
5xx: Server Error - The server failed to fulfill an apparently valid request
서버 에러 : 서버가 유효한 요청을 수행하는데 실패했음
```

---

## 7. Connection Pool ?
#### p7
```
커넥션 풀에 객체를 할당한다.
요청이 올 경우, 할당된 객체가 있으면 할당받는다.
connection pool이 너무 크다면, 메모리 낭비가 심해진다
요청이 올 경우, 할당된 객체가 없다면 대기한다.
따라서 connection pool이 너무 작으면, 대기하는 요청이 많아진다.
적절한 크기로 조정한다.
```

---

## 8. TIME_WAIT와 TCP_Slow_start
#### p8
```
connection이 close 되면, time_wait 발생한다.
기존에 connection됬던 IP주소와 포트번호를 메모리에 저장한다.
발생하는 이유는 같은 IP주소와 포트번호를 사용하는 TCP Connection 생성을 막기위해서다.
결과적으로 포트고갈과 서버부하를 막는다.

TCP_Slow_start는 패킷전송량의경우, Connection 생성시간에 영향을 받는다.
```

---

## 9. http1.0과 http1.1에서의 keep-alive 사용법
#### p9
```
http/1.0 에서는 Request headers에 Connection : keep-alive 항목을 표기한다.
서버는 Response Headers로 Keep-alive : timeout=5, max=100 등을 반환한다.
클라이언트가 커넥션을 동일하게쓰고싶다면, 동일한 헤더를 사용한다.
이 때, 정확한 Content-length와 멀티파트 형식이 중요하다.
시작과 끝이 다르면, 다른 헤더이기때문이다.
HTTP/1.1에는 빠져있지만, HTTP/1.0을 지원해야되기때문에 구현해야한다.

HTTP/1.1은 지속커넥션이다.
끊으려면, Connection:close를 헤더에 명시하면된다.
클라이언트와 서버는 언제든지 header없이 끊을수있다.
```

---

## 10. Latency와 bandwidth란? 그리고 웹 성능을 높이려면?
#### p10
```
latency는하나의 데이터 패킷이 한 지점에서 다른 지점으로 전송되어 이에 소요되는 시간이다. 시간단위는 ms이다.
bandwidth는 단위시간 동안 한지점에서 다른지점으로 전달될 수 있는 최대 데이터양이다. 대역폭(BPS)이라고도 한다.
대역폭은 높이고, 지연성은 낯춘다.
지연성을 낯추는 방법으로는
1. 클라이언트와 서버의 거리를 단축시킨다.
2. 브라우저 캐시 구성한다.
3. 적은 리소스를 로드한다.
그 외 대역폭의 경우, 제한설정을 강제로 높인다.
```

---

## 11. Loadbalancer의 분배방식과 특징은?
#### p11
```
loadbalancer는 클라이언트의 request들을 WAS로 분배하는 역활을 수행
라운드로빈
리스트 컨넥션
리스트 리스펀스 타임
리스트 밴드위스
해싱 메소드
```

---

## 12. Session Clustering ?
#### p11
```
Session 관리가 필요한 이유는 A서버의 세션을 생성한 뒤, C서버로 요청하게되는경우 JSESSIONID가 다르기때문에 다시 Session을 생성해야하는 경우가 생기기때문이다. 예를들면 로그인같은경우다.
따라서 Session 관리방법은 2가지로 Sticky Session과 Session Clustering이다.

Sticky Session은 특정 세션의 요청이 request에 응답을 준 Server에서만 처리하게하는 것이다.
일반적으로 Cookie를 사용하거나, 클라이언트의 IP Tracking을 통해 진행한다.
- AWS ELB는 Cookie를 사용
- HTTP Response의 cookie를 이용
- 해당 클라이언트가 가는 EC2 Instance의 정보를 저장해놓는다.

단점은 특정 서버 Fail 시, 해당 서버에 붙어있는 세션들이 소실될 수 있으며, 특정서버만 과부하가 올 수 있음

Session Clustering은 여러 WAS의 세션을 동일한 세션으로 관리하는 것이다.
- Cluster로 하나로 관리하는 것
새로운 서버가 하나 뜰때마다 새로운 서버의 IP/PORT를 입력해서, 클러스터링 해줘야한다.
Redis를 이용해서 진행가능하다.
```

---

## Reference
[[10분 테코톡] 👩‍🦰희봉의 웹서버 vs WAS](https://youtu.be/NyhbNtOq0Bc).

[[10분 테코톡] 🔮 히히의 OSI 7 Layer](https://youtu.be/1pfTxp25MA8).

[[10분 테코톡] 🎙티거의 Web server vs WAS](https://youtu.be/F_vBAbjj4Pk).

[[10분 테코톡] 🍪쿠기의 Connection Pool & Keep-Alive](https://youtu.be/MBgEhSUOlXo).

[[10분 테코톡] 🎙️효오의 Latency & Bandwidth](https://youtu.be/mFBIwEhvZUY)

[[10분 테코톡] 🐻마틴의 Sticky session & Session Clustering](https://youtu.be/gzKf2BTZToQ)