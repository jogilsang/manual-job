
## DB
### 목차
1. [데이터베이스에서 인덱스에 대해 설명해주세요](#p1)
2. [트랜젝션의 특징에 대해 설명해보세요](#2.)
3. [인덱스의 구조는?](#3.)
4. [인덱스의 최소단위는?](#4.)
5. [인덱스가 효율적인경우와 비효율적인 경우는?](#5.)
6. [어떤값으로 index를 설정할것인가?](#p6)
---

## 1. 데이터베이스에서 INDEX에 대해 설명해주세요
#### p1
```
예를들면 목차의 앞부분 페이지정보다.
INDEX를 사용하지않는, 최악의 경우 책을 전체적으로 다 보게된다.
이걸 full table scan 이라고한다.
full table scan을 하지않기위해 데이터를 사용 할 때, 자주 사용하는 데이터는 디스크가 아니라
메모리에 올리게된다. 이때 인덱스를 메모리에 저장한다.
```  

---

## 2. 트랜젝션의 특징에 대해 설명해보세요  

---

## 3. 인덱스의 구조는?
```
인덱스는 B-Tree 구조이다.
B-tree는 자식노드가 2개이상이다.
child주소를 통해서, row주소를 찾게된다
Range Scan을 할 수 있다.
```

---

## 4. 인덱스의 최소단위는?
```
디스크 IO의 최소단위는 페이지(또는 BLOCK)이다.
인덱스도 페이지로 관리한다.
```

---

## 5. 인덱스가 효율적인경우와 비효율적인 경우는?
```
조회 시 from where 절이 있을경우 효율적이다.
insert,update,delete는 비효율적이다.
인덱스는 update 개념이없기때문에, 테이블에 업데이트 발생시 인덱스에서는 delete후 insert 작업을함
인덱스는 insert 로 값이 들어가게되면, 데이터가 하나씩 밀리고
페이지가 꽉차는경우 새로운 페이지가 생성된다.
인덱스는 delete의경우 삭제하지않고, 사용안함으로 표시한다.
```

---

## 6. 어떤값으로 index를 설정할것인가?
#### p6
```
인덱스 칼럼의 기준은 Cardinality이다.
Cardinality가 높은 칼럼은 number of sort 가 큰 것이다.
예를들면, 주민번호가 닉네임보다 크고, 닉네임이 성별보다 크다
```

---

## Reference
[[10분 테코톡] 👨‍🏫안돌의 INDEX](https://www.youtube.com/watch?v=NkZ6r6z2pBg&list=PLgXGHBqgT2TvpJ_p9L_yZKPifgdBOzdVH&index=80).

[[10분 테코톡] 🦋 레베카의 인덱스](https://www.youtube.com/watch?v=9ZXIoh9PtwY&list=UU-mOekGSesms0agFntnQang&index=49).

[[mysql] 인덱스 정리 및 팁 by 창천향로 창천향로](https://jojoldu.tistory.com/243).
