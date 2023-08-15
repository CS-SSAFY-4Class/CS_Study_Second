# 데이터의 종류 (Data Types)

## Ⅰ. 레지스터에 쓰이는 데이터 종류
- 산술 연산용 숫자
- 데이터 처리용 영문자
- 특수 목적용 기호

## Ⅱ. 진수와 진법

### 1. 진수의 종류
- radix: 진법의 기수에 해당
- 10진수
- 2진수
- 8진수
- 16진수 

### 2. 2진화 진수
- 2진화 8진수(Octal)
  - 2진수를 3bit씩 끊어서 읽음
- 2진화 16진수(Hexadecimal)
  - 2진수를 4bit씩 끊어서 읽음
- 2진화 10진수(BCD: Binary Code Deciaml)
  - 2진수를 4bit씩 끊어서 읽음(1001(9) => 0001 0000(10))

## Ⅲ. 영숫자의 표시

![아스키코드](https://i.namu.wiki/i/fEOmIqjeK_A07aqnNqjs7RY0pPBrQBHh6vDvG8Ex_ASagz26bNBSpvmkEU2iI4Bs43eiVIV6GGaJ2L2gFm6B3A.gif)
- ASCII Code : 7bits (+1 parity bit)
- EBCDIC Code : 16bits, IBM internal code
- UniCode : 16bits / 32bits

<br>

# 보수 (Complements)

## Ⅰ. 기본 개념

###  정의
- 진법의 기수 r에 대응하는 역값
- 뺄셈과 논리 계산에 사용

### (r-1)의 보수 체계
- 9's complement : 99999 - 12389 = 87610
- 1's complement : 1111111 - 0001111 = 1110000

### (r)의 보수 체계
- 10's complement 10000 - 12389 = 87611
- 2's complement 10000000 - 0001111 = 1110001

## Ⅱ. 부호없는 숫자의 뺄셈
- 72532 - 13250 = 59282
  - 72532 + 86750(13250의 보수) = 159282
  - 앞자리 1을 날리면 59282
- 13250 - 72532 = -40718
  - 13250 + 27468(72532의 보수) = 40718
  - 앞에 - 부호

<br>

# 고정 소수점 표현 (Fixed Point Representation)

## Ⅰ. 정의
- 소수점의 위치를 결정하여 숫자를 표현
- 레지스터 비트에 소수점 위치를 표시
- 16bit 정수의 경우 최우측에 소수점 자리 위치
- 부동소수점의 경우, 레지스터 비트 앞/중간에 소수점 자리 위치

## Ⅱ. 정수의 표현 (-14)
- MSB(Most Significant Bit)로 부호 표현
- 양수는 MSB = 0, 음수는 MSB = 1
- 부호 절대값 표현 : 1 0001110
- 부호화된 1의 보수 : 1 1110001
- 부호화된 2의 보수 : 1 1110010

## Ⅲ. 오버플로우

### 1. 오버플로우의 발생
- N자리의 두 수를 더하여 N +1자리의 합이 발생하였을 때
- 가수, 피가수의 부호와 관계없이 발생
- 정해진 레지스터의 비트수로 인한 문제

### 2. 오버플로우 발생상황
- 연산 결과값이 레지스터의 비트 수를 초과할 경우 발생
- 두 수의 부호가 같을 경우에만 발생
- 레지스터에 저장된 연산 결과값은 잘못된 값으로 저장

### 3. 오버플로우 처리 방법
- 오버플로우 발생을 미리 확인
  - MSB의 두 캐리 비트의 값이 서로 다르면 오버플로우
- 연산을 처리하지 않고 인터럽트 또는 에러 처리

<br>

# 부동 소수점 표현 (Floating Point Representation)

## Ⅰ. 부동소수점 표시 방법
- 가수와 지수로 표현
- 가수(mantissa) : 분수, 정수값 표시
- 지수(component) : 십진/이진 소수점 위치를 표시
- ex) 6231.789 = 0.6132789 * 10⁴

![부동소수점](https://blog.kakaocdn.net/dn/ZqdvR/btqFBe5sHME/zY2SEoAgrk0lEeWSuxvZR0/img.png)

## Ⅱ. 정규화(Normalizaiton)
- 부동소수점 숫자에서 최상위 비트가 0이 아닌 경우
- 0이 있을 경우, Mantissa의 소수점 위치 이동
- 이동한 만큼 exponent의 값 변경

<br>

# 기타 이진 코드 (Other Binary Codes)

## Ⅰ. Grey Code
![그레이코드](https://t1.daumcdn.net/cfile/tistory/250A2F3B58C817BC2B)
- 한 숫자에서 다음 숫자로 변할 때 한 비트만 변동
- 제어 계통에 주로 사용
- 여러 전기 신호가 동시에 바뀔 때 낮을 에러 발생률

## Ⅱ. BCD 코드
- 10진수에 대한 2진수 표현
- 4bit를 사용 0~9까지 사용(0000 ~ 1001)

## Ⅲ. Excess-3 Code
- BCD Code + 0011
- 암호 교신의 기본 코드, 파생 암호 발생 방법에 사용

## Ⅳ. 기타 영문 code
- ASCII : 7bits + parity 1bit
- EBCDIC : 8bits + parity 1bit

<br>

# 에러 검출 코드 (Error Detection Codes)

## Ⅰ. Parity bit
- 외부 잡음에 의한 에러 발생의 검출
- 짝수 패리티/홀수 패리티 사용
- 가장 간단하고도 일반적인 방법
- 2개의 비트 동시 에러의 경우 검출 불가능

## Ⅱ. Parity bit의 적용
![패리티비트](https://blog.kakaocdn.net/dn/kzyXf/btraWTqTnIV/NgvHa01LibIlRUD8EKmEG1/img.png)
- 송신측 : 패리티 발생기
- 수신측 : 패리티 검사기
- 수신측 패리티 검사 결과 = 데이터 패리티와 일치
  - 에러없음 (0 출력)
- 데이터 패리티와 불일치
  - 에러 발생(1 출력)


