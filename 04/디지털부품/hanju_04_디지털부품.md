# 집적회로

## Ⅰ. 정의
- 디지털 게이트를 구성하는 전자 부품을 포함하는 실리콘 반도체 칩(Chip)
- 칩 내부에 케이트들이 연결되고, 외부로도 연결
- 칩의 등록 번호로 구분(dataBook을 통하여 정보 확인 가능)

## Ⅱ. 집적 규모에 따른 분류
- SSI : 소규모, 10개 이하의 게이트들로 구성
- MSI : 중규모, 10~200개의 게이트들로 디코더, 가산기, 레지스터 구현
- LSI : 대규모, 200~1000개의 게이트들로 프로세서나 메모리 칩과 같은 디지털 시스템 형성
- VLSI : 초대규모, 수천개 이상의 게이트 집적, 대형 메모리나 마이크로컴퓨터 칩

## Ⅲ. 디지털 논리군
- TTL : Transister-Transistor Logic
    - 일반 로직 회로부품
- ECL : Emitter-Coupled Logic
    - 고속 논리 시스템용 부품(1~2ns 이하), 슈퍼컴퓨터용
- MOS : Motel Oxide Semiconductor
    - 고밀도 집적회로용 부품
- CMOS : Complement Motel Oxide Semiconductor
    - 고밀도 회로, 단순한 제조공정, 저전력 특성

<br>

# 디코더

## Ⅰ. 정의
- N비트의 이진 정보를 서로 다른 2ⁿ개의 원소 정보로 출력
- 2개의 입력 -> 4가지 출력 2X4 decoder
- 3개의 입력 -> 8가지 출력 3X8 decoder

## Ⅱ. NAND 게이트로 이루어진 디코더
![NAND 게이트](https://slidesplayer.org/slide/17710859/105/images/29/03+%EB%94%94%EC%BD%94%EB%8D%94+NAND+%EA%B2%8C%EC%9D%B4%ED%8A%B8%EB%A1%9C+%EA%B5%AC%EC%84%B1%ED%95%9C+%EC%9D%B8%EC%97%90%EC%9D%B4%EB%B8%94%28enable%29+%EC%9E%85%EB%A0%A5%EC%9D%B4+%EC%9E%88%EB%8A%94+%ED%9A%8C%EB%A1%9C.+E%3D0%EC%9D%BC+%EB%95%8C%EB%A7%8C+%EC%B6%9C%EB%A0%A5%EC%9D%B4+%EB%8F%99%EC%9E%91.jpg)
- 기본 정의의 디코더와 0과 1이 반대로된 디코더
- 보수화된 출력이 더 경제적임
- 대부분의 출력 신호가 1로 유지
- CMOS 회로의 영향으로 저전력 회로에 유리

## Ⅲ. 인코더
- 디코더와 반대 동작 수행
- 2ⁿ의 입력에 대하여 N 이진 코드 출력
- 한 번에 하나의 입력만이 1의 값을 가질 수 있음

<br>

# 멀티플렉서와 레지스터

## Ⅰ. 멀티플렉서
![멀티플렉서](https://blog.kakaocdn.net/dn/bsFcL6/btqHAmuVmmZ/TLDt8EkWgMQeo31DgMCYH0/img.png)
- N개의 선택 입력에 따라서 2ⁿ개의 출력을 하나의 출력에 선택적으로 연결
- 다중 입력 중 하나를 선택하여 출력으로 연결
- 네트워크 스위치의 기본 구조 요소
- 위 그림은 4X1 MUX 라고 부름

## Ⅱ. 레지스터

### 1. 레지스터의 구성
- N비트 레지스터 : N비트의 이진 정보 저장
- N개의 플립플롭과 조합 회로로 구성

### 2. 기본 레지스터
- 클럭펄스 타이밍에 입력값이 레지스터에 저장
- 레지스터에 저장된 값은 항상 출력에서 참조 가능
- Clear, Clock 입력 제공

### 3. 병렬로드 가능한 4비트 레지스터
![4비트 레지스터](https://www.researchgate.net/publication/49603927/figure/fig1/AS:305722165350402@1449901252732/4-bit-Parallel-load-Shift-Register.png)
- 4비트의 데이터를 동시에 입력 가능
- Load, Clock 입력 제공
- Load값이 1이 될 때만 레지스터에 값 입력 가능

<Br>

# 시프트 레지스터

## Ⅰ. 정의
![시프트 레지스터](https://upload.wikimedia.org/wikipedia/commons/a/a1/4-Bit_SIPO_Shift_Register.png)
- 레지스터에 저장된 이진 정보를 단/양방향으로 이동 가능한 레지스터
- 각 FF들의 입력이 출력과 cascade로 연결
- 공통의 clock이 다음 상태로의 이동 제어

## Ⅱ. 병렬로드를 가지는 양방향 시프트 레지스터
- 병렬로드, 왼쪽/오른쪽 시프트, 병렬출려 기능
- 동기화된 clock에 의하여 동작
- 범용 레지스터를 지칭

<br>

# 이진 카운터

## Ⅰ. 정의
![이진 카운터](https://mblogthumb-phinf.pstatic.net/20140724_49/miniskirtzia_1406177515898JW26N_PNG/%C1%A6%B8%F1_%BE%F8%C0%BD72.png?type=w2)
- 정해진 순서대로 상태 변이 수행
- Clock 또는 외부 입력에 또는 상태 변이 용도
    - 사건의 발생 횟수 카운트
    - 동작 순서 제어 타이밍 신호 발생에 적용

## Ⅱ. 병렬입력을 가진 이진 카운터
- 카운터의 초기값 설정 가능
- 병렬 입력을 통하여 초기값 로드
- Load, Clear, Incremennt 기능

<br>

# 메모리 장치

## Ⅰ. 정의
- 정보의 입출력 기능을 가지는 저장 요소들의 집합
- Word 단위로 정보를 저장
- Word : 입출력에서 하나의 단위로 취급되는 비트의 그룹
    - 16bit(2byte), 64bit(4byte)
- Btye : 워드의 기본 단위
- MB(10^6byte), GB(10^9byte), PB(10^12byte)

## Ⅱ. RAM(Random Access Memory)
- Word의 물리적인 위치에 관계없이 데이터 접근
- 모든 데이터 위치에 대하여 동일한 접근 시간
- N 비트의 입력 / 출력(word 크기와 동일)
- K개의 주소 라인으로 2^k개 word 중 하나를 선택
- 읽기 / 쓰기 지정(R / W)

## Ⅲ. ROM(Read Only Memory)
- 한 번 저장된 데이터를 읽기만 가능
- 1 word가 N비트이고 M워드를 저장하는 N * M ROM
- ROM에 저장된 M word를 접근할 수 있는 K 개의 주소 입력 (2^K = M)

## Ⅳ. ROM의 종류
- Mask ROM : 석판화(Lithography) 방식으로 구워져 나오는 ROM
- PROM : 한번만 프로그램 가능
- EPROM : UV에 의한 데이터 삭제(ROM 초기화) 및 재프로그래밍 가능
- EEPROM : 전기 신호에 의한 데이터 삭제 / 초기화 및 재프로그래밍

## Ⅴ. ROM의 기능을 하는 RAM
- Flash-RAM : BIOS, USB memory, SD card
- NV-RAM : NON-Volatile RAM, Battery Backup RAM