# 디지털 컴퓨터

## Ⅰ. 정의
- 이진시스템을 사용하여 계산을 수행하는 디지털 시스템
- 비트의 그룹을 사용하여 숫자, 문자 및 기타 정보를 표시 및 처리

## Ⅱ. 컴퓨터 하드웨어

### 1. CPU
- 중앙처리장치, 컴퓨터 그 자체로 정의
- 산술 논리 처리, 데이터의 저장 및 제어

### 2. 주변장치
- 메모리(RAM, ROM)
- 저장 장치(Storage)
- 입출력 장치(IO devices)

## Ⅲ. 컴퓨터 소프트웨어

### 1. 운영체제
- OS : Operating System

### 2. 시스템 프로그램
- 유틸리티, 데이터베이스, Editor
- OS에 포함되거나 연결되어 시스템 운영을 보조
- 아래 한글 같은 프로그램은 시스템 프로그램 X (메모장 같은 건 O)

### 3. 응용 프로그램
- 나머지 거의 모든 프로그램이 이 부류에 속함

<br>

# 논리 게이트

## Ⅰ. 이진 정보의 표시
- 0과 1의 전압 신호
- (0V - 5V) 시스템과 (0.5.V - 3V) 시스템 존재 (전자가 흔히 쓰임)

## Ⅱ. 논리 게이트
![논리게이트](https://mblogthumb-phinf.pstatic.net/20121019_172/leehojun13_1350636845012ai00G_JPEG/%B3%ED%B8%AE%B0%D41.JPG?type=w2)

<br>

# 부울대수

## Ⅰ. 기본 개념
- 이진 변수와 논리 동작을 취급하는 대수
- 기본 대수 동작 : AND, OR, NOT
- ex) F = x + y'z

## Ⅱ. 사용 이유
- 변수 사이의 진리표 관계를 대수적으로 표시
- 논리도의 입출력 관계를 대수 형식으로 표시
- 같은 기능을 가진 더 간단한 회로 발견

## Ⅲ. 부울 대수의 기본 관계

### 1. 기본 법칙
![부울법칙](https://t1.daumcdn.net/cfile/tistory/99DEE84D5ABB2E1B1D)

### 2. 부울 대수 간략화와 등가 회로
- F = ABC + ABC' + A'C
- F = AB(C+C') + A'C (보원법칙 적용)
- F = AB + A'C

### 3. 보울 대수의 보수
- F = AB + C'D' + B'D
- F' = (A'+B')(C+D)(B+D') 

<br>

# 맵의 간소화

## Ⅰ. 맵방식의 부울 수식 간소화
- 부울 함수를 visual diagram을 통해 간소화
- Karnaugh map, Veitch diagram 등이 존재
- Minterm, Maxterm을 이용한 간소화

### 예시(카르노 맵)
![카르노맵](https://velog.velcdn.com/images%2Ftonyhan18%2Fpost%2Fc67e9a48-f6df-4782-841b-ec33ba15c422%2Fimage.png)

## Ⅱ. 간소화

### 1. 논리항의 논리곱
- 1항의 간소화
- 0항의 간소화(구한 후 대수를 구함)

### 2. 무정의 조건
- 1로 써도 되고 0으로 써도 되는 항이 존재
- 이러한 항들을 활용하여 간소화

<br>

# 조합 회로

## Ⅰ. 정의
- n개의 입력조합(2ⁿ가지)
- 입력조합이 들어가는 논리 게이트의 집합
- 논리 게이트에 의해 도출되는 출력값

## Ⅱ. 종류

### 1. 반가산기
- 1bit 2진수 두 개를 더한 값(S)과 자리올림수(C)
![반가산기](https://t1.daumcdn.net/cfile/tistory/225C2C3758A97D2904)

### 2. 전가산기
- 1bit 2진수 세 개를 더한 값(S)과 자리올림수(C)
![전가산기](https://i.namu.wiki/i/i6lvIFoFkVX8NKI4dIv6WCJ6_2gp_oC9SEDHilexBoFPaiehsCgtPQc4nxCwyeJx1-hunFVMh8OVze0OeuPpew.webp)

<br>

# 플립플롭

## Ⅰ. 플립플롭의 정의
- 1 비트의 디지털 정보를 저장하는 이진 셀(디지털 메모리)
- 동기식 순차회로의 기본적인 요소로 사용
- 조합회로와 함께 순차회로를 구성
- 입력 상태가 변화를 일으키지 전까지는 이전의 출력 상태를 그대로 유지

## Ⅱ. 플리플롭의 종류
![플립플롭](https://t1.daumcdn.net/cfile/tistory/2467373B5963B8E037)
- NA 결과값은 안 나오게 조심
- Q는 이전 결과값
- 입력값이 들어와도 C(Clock)가 들어오지 않으면 무반응

## Ⅲ. 모서리 변이형 플립플롭

### 1. 입력값의 변화 모서리에서만 동작
- Upward triggered FF
    - 입력값이 상향일 경우에만 동작(0 -> 1)
- Downward triggered FF
    - 입력값이 하향일 경우에만 동작(0 -> 0)
- 위에서 말하는 입력값은 Clock

### 2. 올바른 동작을 위해서는 최소의 신호 유지 시간 필요
- Setup time
    - 출력 변화를 위하여 입력이 유지되어야 하는 최소 시간
- Hold time
    - 출력 유지를 위하여 입력이 바뀌지 않아야 하는 최소 시간
- 여기서 말하는 입력은 Clock 이외의 입력값

<br>

# 순차회로

## Ⅰ. 정의
![](https://mblogthumb-phinf.pstatic.net/MjAyMDAxMDNfOSAg/MDAxNTc4MDEzMzY3Mzc2.LhCecH3pRI7ull-vW3pFPt5zhbYvaONF1biOjUY4iH0g.ftHdAQRzn8LesEuDkT-0jhzaXaloMdZC7OJ1MJ26ybwg.PNG.cni1577/%EC%BA%A1%EC%B2%98.PNG?type=w800)
- 플립플롭과 조합회를 서로 연결한 회로
- 클럭펄스에 의하여 동기화된 입력 순차에 의하여 제어
- 출력은 외부 입력과 플립플롭의 현 상태의 함수로 표시