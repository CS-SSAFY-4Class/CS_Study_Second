# 레지스터 전송 언어

## Ⅰ. 마이크로 연산
- 레지스터에 저장된 데이터를 가지고 실행되는 동장
- 하나의 clock 시간동안 실행되는 기본 동작

## Ⅱ. 레지스터 전송언어
- 마이크로연산, 전송을 간단하고 명료하게 표시하기 위하여 사용하는 기호
- 디지털 컴퓨터의 내부 조직을 상세하게 나타내는 수단으로 사용
- 디지털 시스템의 설계 편의성 제공

## Ⅲ. 레지스터 전송 언어 규칙
![레지스터 전송 언어 규칙](https://blog.kakaocdn.net/dn/bwzbOp/btqCU7PLfdT/FlOEP0ZZ9n2vQGdU6phCM0/img.png)
- 대문자로 표시(MAR, MBR, AC, PC, DR ...)
- 레지스터 가장 왼쪽 => MSB 가장 오른쪽 => LSB

<br>

# 레지스터 전송

## Ⅰ. 레지스터 정보 전송
- 치환 연산자 사용
  - R2 <- R1
- 제어 조건이 있을 경우
  - if (P = 1) then (R2 <- R1)
- 제어 함수로 표현할 경우
  - P: R2 <- R1
  - P? R2 = 0 : R1 = 0
  - R2에는 t+1 타이밍에 전송 완료
- Register data exchange
  - T: R2 <- R1, R1 <- R2

<br>

# 버스와 메모리 전송

## Ⅰ. 공통 버스
![공통 버스](https://velog.velcdn.com/images%2Funderlier12%2Fpost%2F98d68d7b-eee3-4cbe-ad29-20833fb2e659%2Fimage.png)
- 레지스터들 사이의 전송 통로
- 한 번에 하나의 신호만 전송하도록 제어
- 멀티플렉서를 사용하여 레지스터 선택

## Ⅱ. 상태 버퍼
- 멀티플렉서 대신 사용하여 버스 구성 가능
- 3개의 상태로 동작
  - 논리0, 논리 1 : 정상적인 버퍼로 동작
  - 고저항 상태 : 출력 차단

## Ⅲ. 메모리 전송
- Read : DR <- M[AR]
- Write : M[AR] <- R1 

<br>

# 산술 마이크로 연산

![산술 마이크로 연산](https://velog.velcdn.com/images%2Funderlier12%2Fpost%2F19007420-7632-490d-97dc-3155987d6eb1%2Fimage.png)

## Ⅰ. 마이크로 연산의 분류
- 레지스터 전송 마이크로 연산 : 레지스터간 이진 정보 전송
- 산술 마이크로 연산 : 수치 데이터에 대한 산술 연산
- 논리 마이크로 연산 : 비수치 데이터에 대한 비트 조작 연산
- 시프트 마이크로 연산 : 데이터에 대한 시프트 연산

## Ⅱ. 이진 가산기
두 비트와 이진 캐리의 산술합을 계산
- 여러 개의 전가산기를 연결

## Ⅲ. 이진 감가산기
- 보수를 만드는 게이트와 신호 사용
  M -> 0 : 가산
  M -> 1 : 감산
- A(0-3), B(0-3), S(0-3)는 bus에 연결

## Ⅳ. 산술 회로
- 4개의 전가산기
- 4개의 멀티플렉서
- 2개의 4비트 입력(A, B)
- 1개의 출력 (D)
- 3개의 제어 라인(S1, S0, Cin)

<br>

# 논리 마이크로 연산

![논리 마이크로 연산](https://user-images.githubusercontent.com/38898759/114565500-48864880-9cac-11eb-95d0-5bf14b4c17d2.jpg)

## Ⅰ. 논리 마이크로 연산의 하드웨어 구현
![논리 마이크로 연산의 하드웨어 구현](https://blog.kakaocdn.net/dn/mjwJ9/btqCWL6j2cZ/fLms3cXY6q4RHOdva5Ycy0/img.png)

<br>

# 시프트 마이크로 연산
![시프트 마이크로 연산](https://postfiles.pstatic.net/MjAyMDEwMTVfMzEg/MDAxNjAyNjkwNTA4MDg1.MwFORqj7JrCR9pxkDeb2X4GLXgtpViw0ctNF0Hr3lyUg.jBOLUK1Gw6ImSue4_3VYulNahvDWhoziBp-IJgOq034g.PNG.heelieben/image.png?type=w773)

## Ⅰ. 논리 시프트
- 직렬 입력으로 0이 전송
  - R1 <- shl(R1)
  - R2 <- shr(R2)

## Ⅱ. 순환 시프트
- 직렬 출력이 직렬 입력으로 전송
  - cir, cil

## Ⅲ. 산술 시프트
- 부호 비트를 제외하고 시프트
- 왼쪽 시프트 : x2
- 오른쪽 시프트 : /2

## Ⅳ. 4비트 조합회로 시프터
![4비트 조합회로 시프터](https://blog.kakaocdn.net/dn/vWuPP/btqCZzcOx0W/7Ff6gPsLLUv1HW0UX89rg1/img.png)