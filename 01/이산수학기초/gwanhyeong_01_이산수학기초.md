# 1강 이산수학 개요
- 불연속적인 숫자를 다루는 수학
- 컴퓨터를 위한 수학, 참과 거짓으로 살펴보는 컴퓨터 수학, 전산, 정보 수학, 1학년이나 처음 컴퓨터를 배우는 입장에서 배우게됨, 자료구조 또는  알고리즘의 베이스, 논리적 사고, 컴퓨팅 사고력 향상
- 참과 거짓, 0과 1로 살펴볼 수 있는 컴퓨터 수학
- 조금 더 보편적인 컴퓨터 수학, 컴퓨터 안에서 모든 분야에서 쓰이는 이산수학
- 논리적인 흐름이나 컴퓨팅 사고를 배우는 데 도움이 됨


# 2강 명제와 연산자
### 명제

- 진실 혹은 거짓으로 진리를 구분할 수 있는 문장
- 명제는 0 또는 1만을 가지는 컴퓨터 메모리처럼 항상 참과 거짓 둘 중 하나의 값만을 가짐
- 여러 개의 명제를 조합 가능
> ex) 11은 소수이다 -> 명제(참), 컴퓨터는 재미가 없다 -> 명제가 아님

### 연산자로 명제 다루기

- 연산자는 명제를 연산하기 위한 도구
- 이산수학의 기본 연산자로는 6가지

1. Not
    명제 P가 True일 때 Not P은 False


2. And
    P 와 Q 두 명제 모두 참일때만 참

3. Or
    P 와 Q 중 하나라도 참이면 참

4. Exclusive Or
    P와 Q 둘 중 하나만 참일때만 참
5. Implication
    P->Q
    |P|Q|P->Q|
    |:---:|:---:|:---:|
    |T|T|T|
    |T|F|F|
    |F|T|T|
    |F|F|T|
6. Biconditional
    쌍방조건명제: 두 명제의 진리값이 같을 때 참


# 3강 역, 이, 대우
- 진리표: 각 명제 사이의 관계식의 진릿값을 보여주는 표
- 합성 명제의 진릿값을 풀어낼 수 있음


- 역, 이, 대우는 조건명제에서 사용됨


- 역
    ex) q->p


- 이
    ex) ~p -> ~q


- 대우는 본 명제와 진릿값이 같음 / 어떠한 조건 명제를 증명하기 위해 사용
    ex) ~q -> ~p


# 4강 동치 관계

# 동치


## 동치의 의미

- 동치란, 논리적으로 일치한다는 의미
- 흔히 동치는 같은 의미를 가진 더 쉬운 명제를 발견하는 데 사용한다.
- 동치법칙에는 다양한 종류가 있다.


## 동치법칙을 이용해 증명하기

- 굉장히 복잡해 보이는 합성명제라도 간단한 명제로 바꿀 수 있다.


### 논리적 동치(Logical Equivalence)

|Equivalence|Name|
|---|---|
|~(p ∧ q) = ~p ∨ ~q , ~(p ∨ q)= ~p ∧ ~q|드모르간 법칙|
|p ∨ (p ∧ q) = p , p ∧ (p ∨ q) = p|흡수 법칙|
|p ∨ ~p = T , p ∧ ~p = F|부정 법칙|
|p -> q = ~p ∨ q|함축 법칙|

    ex) 동치법칙을 이용해서 (p->q)∧(p->~q)을 간소화하라
        (~p ∨ q) ∧ (~p ∨ ~q ) 함축법칙
        ~p ∨ (q ∧ ~q) 분배 법칙
        ~p ∨ F 부정 법칙
        ~p 항등 법칙
    
    ex2) 동치법칙을 이용해서 다음 합성명제가 서로 동치임을 증명하라
        ~(p ∨ ~q) ∨ (~p ∧ ~q) = ~p
        pf) (~p ∧ q) ∨ (~p ∧ ~q) 드모르간 법칙
            ~p ∧ (q ∨ ~q) 분배 법칙
            ~p ∧ T 부정 법칙
            ~p 항등 법칙
