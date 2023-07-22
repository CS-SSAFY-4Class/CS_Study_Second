# 알고리즘 그래프

<br/>

## 알고리즘(Algorithm)

- 정의
    - 문제를 해결하기 위한 절차나 방법
    -  수학이나 컴퓨터과학에서 말하는 알고리즘은, 보통 반복되는 문제를 풀기 위한 작은 프로시저(진행절차)를 의미한다. 
- 유래
    - 이 단어는 페르시아의 수학자인 알-콰리즈미의 이름에서 유래했다고 알려졌다. 아라비아 기수법을 나타내는 algorism도 같은 어원을 가진다.

![image](https://blog.kakaocdn.net/dn/xCxbD/btq3zN4NQ3x/0ZBXlRgaeTqT1hBmPBrOQk/img.png)

### 알고리즘 조건 
```
입력 - 알고리즘은 0 또는 그 이상의 외부에서 제공된 자료가 존재해야한다.
출력 - 알고리즘은 최소 1개 이상의 결과를 가져야한다.
명확성 - 알고리즘의 각 단계는 명확하여 애매함이 없어야 한다.
유한성 - 알고리즘은 단계들을 유한한 횟수로 거친 후 문제를 해결하고 종료해야 한다. 
효과성(수행가능성) - 알고리즘의 모든 연산들은 사람이 종이와 연필을 이용하여 유한한 시간 안에 정확하게 수행할 수 있을 정도로 충분히 단순해야 한다.
```
### 알고리즘 평가
- 일반적으로는 알고리즘을 효율성으로 평가하고
- 컴퓨터는 시간과 메모리라는 두 자원을 얼마나 소모하는지에 대하여 중점으로 둔다.
    - 시간 복잡도
        - 알고리즘의 소요 시간을 정확히 평가할 수는 없으므로, 자료의 수 n이 증가할 때 시간이 증가하는 대략적인 패턴을 시간 복잡도라는 이름으로 나타내게 된다. 이를 Big-O 표기법(Big O notation)으로 주로 나타낸다. 
            - O(n)의 시간복잡도 : 크기 n에 비례하는 수의 연산을 수행한다고 보면 된다.  
            
        <- 공간 복잡도도 마찬가지

<br/>

## 오일러 순환과 해밀턴 순환 -> 그래프

### 그래프
- 정점(V)의 집합과 선(E)의 집합으로 구성되며 **G = {V, E}**

### 오일러 순환
- 오일러 경로
    - 그래프의 모든 선을 한번만 방문하는 경로
    - 2개 이상의 정점을 갖는 루프가 없는 연결 그래프에서 홀수 차수 정점이 0 OR 2개만 존재하는 경로
- 오일러 순환
    - 시작점과 끝점이 동일한 오일러 경로
    - 홀수 차수 정점이 0개인 그래프
- 시간 복잡도
    - N <= n(n-1) <= n^2
    - O(n^2) O(n*m)

    ![image](https://search.pstatic.net/sunny/?src=https%3A%2F%2Fi.namu.wiki%2Fi%2FIOLVwBW8UvdylJYGKuFnB0GNdG7Ern7y6eL_UMKTZ1OkuIr56-ea8ssujbAPcvuIgQqVMIJ23eGWiUmyaT64Jg.webp&type=sc960_832)
    v
<br/>

### 해밀턴 순환
- 해밀턴 경로
    - 그래프 G에서 모든 정점(V)을 정확히 한번만 지나는 경로
- 해밀턴 순환
    - 시작점과 끝점이 같은 해밀턴 경로
- 해밀턴 경로 해결 방법
    - 브루트포스
- 시간 복잡도
    - O(x^n) (x는 간선의 갯수, n은 정점의 수)

  ![image](https://postfiles.pstatic.net/MjAyMTA1MjlfMTIz/MDAxNjIyMjk0NzQ5NzU2.vh15apmtAHIWNS-b3Tm3BtkqaDC_9UnrU2JnKILNtqEg.6InQWkiujBXNB_Um66UJcw4Seh0OcLPlx2SZSLLbKO0g.PNG.chgy2131/image.png?type=w966)
  ![image](https://postfiles.pstatic.net/MjAyMTA1MjlfNjAg/MDAxNjIyMjk0ODAyMzk2.jA3jFZR3FBatdRwelhCE-oIc_nbCp0ITYOftbFoqiTkg.eenYUp5ZsX2u57k-P_ZnGODMv6FwIq8bjnLWfSdITmsg.PNG.chgy2131/image.png?type=w966)

<br/>

## 최소신장 트리
- 정의
    - 연결 그래프의 연결된 간선 일부를 사용하여 모든 정점을 포함하여 가중치의 합이 최소가 되는 트리

- 최소 신장 트리의 특징
    - 모든 정점 포함
    - 비순환 구성
    - 최소 비용

![image](https://i0.wp.com/blog.skby.net/wp-content/uploads/2018/11/1-63.png?resize=640%2C236)

- 최소 신장트리 대표 알고리즘
    - prim 알고리즘
    - kruskal 알고리즘
    - solin 알고리즘

- 실생활 사용 용도
    - 도로 건설
    - 전기회로
    - 통신
    - 배관
    - 네트워크

<br/>

## 최단경로 알고리즘
- 통신에서 네트워크의 성능을 평가할 때 최단 경로 또는 최소 비용을 선정한다.
    - 비용 : 네트워크의 각 링크에 부여된 통신 비용
    
- 대표 알고리즘
    - Dijkstra 알고리즘
    - Bellman-Ford 알고리즘
![image](https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAyMjAzMThfMTIw%2FMDAxNjQ3NTc4NTQ4ODc2.MV--A-uOy8y8b44zDkFwh_emDcQexxZRSfopEDjpcsgg.B0_3ykeEoCNzacLTbSmXoZupV4r6ZtkbSAUkkRuyth4g.PNG.twonkang00%2Fimage.png&type=sc960_832)
