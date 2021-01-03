
### 산술 우측 쉬프트 (ArithMeticRightShift)
```
전체가 오른쪽으로 이동하지만, 왼쪽부호 값은 보존된다.
반복 시, 음수인경우 -1로 수렴
반복 시, 양수인경우 0으로 수렴
```

### 논리 우측 쉬프트 (logicalRightShift)
```
전체가 오른쪽으로 이동한다. 왼쪽부호 값은 보존되지않으며, 0이 체워진다.
반복 시, 음수이던 양수던 0으로 수렴한다.
```

### 2의보수 


### 비트 확인하기 
```java
int getBit(int num, int i) {

if( num & (i << 1) !=0 ) {
  return 1;
}else {
  return 0;
}

}

```

### 비트 채우기 (1)
```java
int setBit(int num, int i) {
    // 1 << i = 000010000
    // OR연산 : i번째 비트가 1이면 해당 숫자는 바뀌고, 그 외 숫자는 기존값과 동일
    return num | ( 1 << i );
}
```

### 비트 지우기 (0)
```java
int clearBit(int num, int i) {
   // ~(1 << i) = 1111101111111
   // AND연산 : i번째 비트가 0이면 해당 숫자는 0이되고, 그 외 숫자는 기존값과 동일 
   return num & (~(1 << i));
}
