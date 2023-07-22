# 형식 언어, 오토마타, 셈

<br/>

## 형식 언어와 정규언어
- 형식 언어 : 구조 범위 등이 명확하게 규정되고 정의된 인공 언어 -> 어학, 논리, 프로그래밍 등을 위하여 어법을 형식화하여 기술한 것 

- 정규 언어
    - 정규 언어(regular language)는 이론 전산학, 형식 언어 이론에서 정규 표현식을 이용하여 표현할 수 있는 형식 언어이다.

    - 정규 언어는 유한 상태 기계가 인지하는 언어로 정의할 수도 있다. 정규 표현식과 유한 상태 기계의 등가성은 클레이니의 정리로 알려져 있다. 촘스키 위계에서 정규 언어는 3형 문법(정규 문법)에 의해 생성되는 언어로 정의된다.

![image](https://postfiles.pstatic.net/MjAxOTEyMjVfMTA1/MDAxNTc3MjQ2NTU2MDUy.UDu9ADqQDw5yjw0BY1IcTud5ywVedpslC1eSd9C-KQ4g.Y9J7-FpohfdbVc6lRvlpGbj-CUzdirRmr8I3rIC3fIEg.PNG.bestowing/image.png?type=w966)

<br/>

## 정규식과 정규문법
- 정규 문법(regular grammar)은 정규 언어를 기술하는 형식 문법
    - 우선형 문법
        - 4-튜플에서 생성 규식 P가 밑 수식 3개로 구성되어 있음
![imgae](https://wikimedia.org/api/rest_v1/media/math/render/svg/06315a34a5aa667843d00ca620d3fd8010dda393)
![imgae](https://wikimedia.org/api/rest_v1/media/math/render/svg/70c01063c63dc3c664bdf7fc8f8c1e482ff51be8)
![imgae](https://wikimedia.org/api/rest_v1/media/math/render/svg/8c3117f8a1f999426563706d181967857de9dca3)

    - 좌 선형 문법
        - 4-튜플에서 생성규치 P가 아래 3개로 구성되어 있는 것
![imgae](https://wikimedia.org/api/rest_v1/media/math/render/svg/06315a34a5aa667843d00ca620d3fd8010dda393)
![imgae](https://wikimedia.org/api/rest_v1/media/math/render/svg/e34e93564e485feee0d142f9173f7a97a2203ded)
![imgae](https://wikimedia.org/api/rest_v1/media/math/render/svg/8c3117f8a1f999426563706d181967857de9dca3)

- 정규 문법은 정규 언어를 표현하는 문법으로 유한 오토마타, 정규식과 완벽하게 대응한다.

<br/>

## 유한상태기계 오토마타와 언어
- 유한 상태 기계 = 오토마톤 -> 복수형 : 오토마타
- 정의
    - 컴퓨터 프로그램과 전자 놀리 회로를 설계하는 데에 쓰이는 수학적 모델 (상태 기계)
    - 특정한 유한 오토마톤은 현재 상태로부터 가능한 전이 상태와, 이러한 전이를 유발하는 조건들의 집합

-결정적 유한 오토마타(Deterministic Finite Automata, DFA)
    - Q는 상태의 공집합이 아닌 유한 집합
    - Σ 는 입력 문자 (유한하며, 비어있지 않은 기호의 집합이다).
    - ![image](https://wikimedia.org/api/rest_v1/media/math/render/svg/3086070a07409fa7e760fea6e7c932b2a590b1ce) 는 상태 전이 함수 : ![image](https://wikimedia.org/api/rest_v1/media/math/render/svg/3d1a39532108e9c593fbc41b52c8caf29c26cd4d)
    - s0는 초기 상태이며, Q의 원소
    - F는 최종 상태의 집합, Q의 원소

- 비결정적 유한 오토마타(Nondeterminstic Finite Automata, NFA)
    - Q는 상태의 공집합이 아닌 유한 집합
    - Σ는 입력 문자 (유한하며, 비어있지 않은 기호의 집합이다)
    - S는 유한하며, 비어있지 않은 상태의 집합
    - ![image](https://wikimedia.org/api/rest_v1/media/math/render/svg/3086070a07409fa7e760fea6e7c932b2a590b1ce)는 상태 전이 함수 : ![kimage](https://wikimedia.org/api/rest_v1/media/math/render/svg/ee5c2b60a1753b2c4a923706b030f62f488dff6f)
    - s는 초기 상태, Q의 원소
    - F는 최종 상태의 집합, Q의 원소

비결정적 유한 오토마타는 결정적 유한 오토마타와는 다르게 입력 기호에 대해서 
![image](https://wikimedia.org/api/rest_v1/media/math/render/svg/274c9edc4f01b46f40dd856fe9eceeeb6c0a56a9) -transition 에 의해 0개 이상의 이동이 가능

<br/>

## 스트링 매칭 알고리즘
- 주어진 텍스트에서 주어진 패턴이 어디에 나타나는지를 알아내는 문제
    - 직선적 알고리즘
        - 텍스트의 각 위치에서 시작하는 부분 스트링이 패턴과 일치하는지 조사
        - ![image](https://postfiles.pstatic.net/MjAyMjExMTVfMjM2/MDAxNjY4NDQxNTIxOTgy.yCxQw7I9QesjWvr6vAFjkS387mLtc7mDV3Gc1kaYJSog.Dmf1kH5kHQkf-6hy_ljVXY7blCw3rJMlJ89o3M4vqb8g.PNG.gnsdudwkd/image.png?type=w773)

    - 라빈-카프 알고리즘
        - 스트링을 숫자값으로 바꾸어 hash값을 계산하여 매칭하는 알고리즘

    - 유한 상태 자동 장치와 스트링 매칭
        - ![image](https://postfiles.pstatic.net/MjAyMjExMTZfOTMg/MDAxNjY4NTgyMTM1ODIx.qnMvBVJLvZ1JMiO2QvOM4LRg6q2qFMcAmEI1-BVC01kg.EllrdTcQXg9V9RP-QXjQRQRpy3XZAPdW3EzPO5OkciEg.PNG.gnsdudwkd/image.png?type=w773)

    - KMP 알고리즘
        - 패턴을 전처리하여 접미부와 일치하는 최대 접두부를 구하는 방식


