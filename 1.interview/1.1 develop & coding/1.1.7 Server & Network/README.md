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
13. [JSESSIONKEY란?](#p13)
14. [TLS와 SSL의 차이, 프로세스는?](#p14)
15. [DNS의 통신구조와 질의과정 프로세스는?](#p15)
16. [메모리의 정의는?](#p16)
17. [프로세스의 크기보다 할당받은 메모리의 크기가 작다면?](#p17)
18. [가상메모리를 확인하거나 모니터링하는 방법은?](#p18)
19. [프로세스와 File I/O 과정은?](#p19)

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

## 13. JSESSIONKEY ?
#### p13
```
웹 브라우저에서 사용중인 서비스에 대한 로그인을 한 뒤, 자유롭게 이용할 수 있는것은 바로 세션이 유지되기때문이다.
세션이 유지된다는 건, Cookie 등을 활용하기 때문이다.
HTTP프로토콜은 요청 시 연결이 생성되고, 응답 후 연결이 끊어진다
따라서 Cookie를 통해 상태를 저장하고 세션을 유지하게된다.

Tomcat Container의 경우, Session에 대해서 JSESSIONID를 발급한다.
클라이언트는 Header에 쿠키값을 넣고 이를통해 서버에 요청하며, 서버는 세션 메모리에 값들을 유지한다.

Q. 도메인이 다르게될경우, Session유지???
```

---

## 14. TLS와 SSL의 차이, 프로세스는?
#### p14
```
TLS(Transport Layer Security)는 데이터 암호화 관련내용으로 상대방과 미리 주고받은 key로 응용계층에서 전송계층으로 암호화해서 전달하고, 전송계층에서 응용계층으로 복호화되어 전달되는 것이다.
Message는 key값과 MAC(Message Authentication Code)이 포함되어 전달된다.

HTTPS 기반의 TCP 443 포트이다.
예전에 SSL이 있었고 SSL 3.0이, TLS 1.0으로 변환되었다. 
암호화(Encryption)와 인증(Authentication), 무결성(Integrity)의 특징이있다.
```

---

## 15. DNS의 통신구조와 질의과정 프로세스는?
#### p15
```
DNS를 사용하는 이유는 ip가 아닌 도메인이름으로만으로 접속이 가능하게 하기때문이다.
DNS 통신구조는 localhost에서 첫번째로 hosts 파일 접근 후, 도메인정보가 있는지 확인한다.
두번째는 DNS(Domain Name Server)에 접근해서, 도메인 정보가 있는지 확인한다.
DNS Query에 대한 Data Section은 세 가지이다.
첫번째는 Query name String으로, 일반적인 도메인주소다
두번째는 Type으로, A (Address)와 NS (Name Server)다. A에 대한 응답은 IP이며, NS에 대한 응답은 NameServer 주소다.
세번째는 Class로 IN (인터넷) 고정이다.

host는 Public DNS(KT, SKT, LG U+, Google)에 질의를 하게된다.
해당 Public DNS는 자체적으로 도메인정보가 담긴 Record가 없으며, 다른 DNS에 질의를 한다.
첫번째로 Root name Server(.kr, .com)에 질의를 해서, Top Level Domain - NS 서버주소 (EX : naver.com)를 받아온다.
두번째로 Top level Doamin에 질의를 해서, 그 외 하위 레벨 도메인정보를 질의를 반복하고 최종적으로 IP를 받아서, host에게 전달한다.
```

## 16. 메모리의 정의는?
#### p16
```
메모리란, 넓은 의미로는 기억장치 전부를 뜻하고, 좁은 의미로는 메인 메모리(RAM)를 나타낸다.
메모리 관리가 중요한 이유는 프로세스는 메모리에 적재한 후에 실행하기때문에, 메모리공간을 필요로 하는 프로세스들을
위해 메모리를 관리하고 운영해야한다.
```

---

## 17. 프로세스의 크기보다 할당받은 메모리의 크기가 작다면?
#### p17
```
예를들어, 메모리에서 1MB의 크기만 사용하라고 할당 받았는대, 여기서 2MB의 프로그램을 어떻게 실행 할 수 있는가?
메모리 오버레이(Memory overlay)를 사용한다.
실행해야될 프로그램의 크기가 할당받은 실제 메모리보다 클 때, 전체 프로그램을 메모리에 가져오는 대신 잘라서 가져오는 기법이다.
잘라서 가져온 메모리를 가상메모리(하드드스크나 SSD 같은 보조기억장치를 이용해서 실제 메모리처럼 사용)에 스와핑한다.
스왑아웃은 메모리에서 가상메모리로 스왑하는 것이고, 스왑인은 가상메모리에서 메모미로 스왑하는 것이다.
스와핑이 발생한다는건, 가상메모리를 사용한다는 것이고 스왑하는 비용으로 큰성능저하가 발생한다.
스와핑이 발생하지않으려면,메모리의 여유가 필요하다.
```

---

## 18. 가상메모리를 확인하거나 모니터링하는 방법은?
#### p18
```
리눅스에서는 vmstat 명령어로 딜레이와 횟수를 인수로 넣어서 모니터링할 수 있다.
출력값 중에 free와 so가 있는대, free는 사용가능한 메모리양이고 so는 스왑아웃 값이다
free가 낮고, so가 높으면 좋지않은 상태이다.
```

---

## 19. 프로세스와 File I/O 과정은?
#### p19
```
프로세스가 파일IO을 하게되면, 리눅스에서는 한번 읽은 파일의 내용을 메모리에 파일캐시해 두었다가 사용한다.
파일캐시의 경우 buffer와 cache가 있다
buffer는 파일의 메타데이터를 블록단위로 저장하고, cache는 파일의 내용을 저장한다.
파일캐시는 전체메모리 대비 최대 크기 30%이하 유지를 권장한다.
```

---

## Reference
[[10분 테코톡] 👩‍🦰희봉의 웹서버 vs WAS](https://youtu.be/NyhbNtOq0Bc).

[[10분 테코톡] 🔮 히히의 OSI 7 Layer](https://youtu.be/1pfTxp25MA8).

[[10분 테코톡] 🎙티거의 Web server vs WAS](https://youtu.be/F_vBAbjj4Pk).

[[10분 테코톡] 🍪쿠기의 Connection Pool & Keep-Alive](https://youtu.be/MBgEhSUOlXo).

[[10분 테코톡] 🎙️효오의 Latency & Bandwidth](https://youtu.be/mFBIwEhvZUY)

[[10분 테코톡] 🐻마틴의 Sticky session & Session Clustering](https://youtu.be/gzKf2BTZToQ)

[[10분 테코톡] 👶에단의 TLS](https://youtu.be/EPcQqkqqouk)   

[[10분 테코톡] 🧑‍💻🧑‍💻동글&라면의 DNS](https://youtu.be/5rBzHoR4F2A)   