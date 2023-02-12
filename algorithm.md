# ⭐ 알고리즘(Algorithm), 코딩 테스트

## 💡 알고리즘(Algorithm), 코딩 테스트란?

- 알고리즘: 어떤 **문제**(input을 넣었을 때, 원하는 output이 나오도록 하는 것)를 해결하기 위한 일련의 정해진 절차나 행동
- 코딩 테스트: 코딩을 통한 **문제 해결 능력**을 테스트하는 것
  - 문제 의도를 정확히 파악하고 적절한 해결 방법을 적용할 수 있는가?
  - 해결 방법을 프로그래밍을 통해 능숙하게 구현할 수 있는가?
- 코딩 테스트 문제 풀이 사이트
  - [백준 온라인 저지(BOJ)](https://www.acmicpc.net/) : 가장 많이 사용하는 플랫폼으로 최다 문제 보유, 유형별·단계별 문제 제공
  - [프로그래머스(Programmers)](https://programmers.co.kr/) : 실제 코딩 테스트 환경과 유사, 카카오 기출문제 제공
  - [SW Expert Academy(SWEA)](https://swexpertacademy.com/main/main.do) : 삼성전자에서 제작한 플랫폼, 삼성 SW 역량 테스트 문제 다수 보유
  - [LeetCode](https://leetcode.com/) : 해외 대표적인 코딩 테스트 플랫폼
- `Tip!`
  - 변수명 대충 짓지 않기
  - 언어가 가지는 내장 함수, 라이브러리를 적극 활용하기
  - 반복되는 코드는 함수화를 통해 가독성 있게 작성하기
  - **면접을 위해 풀이를 남에게 설명하는 연습 필수**

## 💡 시간 복잡도 & 빅오 표기법

- 시간 복잡도(Time Complexity): 알고리즘의 수행 시간
  - 시간 복잡도가 높다 -> 느린 알고리즘
  - 시간 복잡도가 낮다 -> 빠른 알고리즘
- 빅오(Big-O) 표기법: 입력 n이 무한대로 커진다고 가정하고 시간 복잡도를 간단하게 표시하는 것
  - O(1): 단순 산술 계산(덧셈, 뺄셈, 곱셈, 나눗셈)
  - O(logN): 크기 N인 리스트를 반절씩 순회/탐색(이진 탐색(Binary Search), 분할 정복(Divide & Conquer))
  - O(N): 크기 N인 리스트를 순회(리스트 순회, 1중 for 문)
  - O(NlogN): 크기 N인 리스트를 반절씩 탐색\*순회(높은 성능의 정렬(Merge/Quick/Heap Sort))
  - O(N^2): 크기 M, N인 2중 리스트를 순회(2중 리스트 순회, 2중 for 문)
  - O(N^3): 3중 리스트를 순회(3중 리스트 순회, 3중 for 문)
  - O(2^N): 크기가 N인 집합의 부분 집합
  - O(N!): 크기가 N인 리스트의 순열(크기가 N인 순열)
- 같은 Output을 만드는 알고리즘이라도 시간 복잡도에 따라 성능이 달라질 수 있고 시험에서 정답 여부가 갈리는 포인트가 될 수 있음

## 💡 데이터 구조

- 스택(Stack)
  - stack은 쌓는다는 의미로, 접시를 쌓고 빼듯이 **데이터를 한쪽에서만 넣고 빼는 구조**
  - 가장 마지막에 들어온 데이터가 가장 먼저 나가므로 **LIFO(Last-in First-out, 후입선출)** 방식
  - 브라우저 히스토리, ctrl + z, 단어 뒤집기에 주로 쓰임
  - 괄호 매칭, 함수 호출(재귀 호출), 백트래킹, DFS(깊이 우선 탐색)에 활용
  - 파이썬은 리스트(list)로 스택을 간편하게 사용 가능
    - .append(): 리스트의 끝에 항목을 더함
    - .pop(): 리스트의 마지막 항목을 삭제하고 돌려줌
- 큐(Queue)
  - queue는 **한쪽 끝에서 데이터를 넣고 다른 한쪽에서만 데이터를 뺄 수 있는 자료 구조**
  - 가장 먼저 들어온 데이터가 가장 먼저 나가므로 **FIFO(First-in First-out, 선입선출)** 방식
  - 순서와 대기, 프로세스 관리(데이터 버퍼), 클라이언트/서버(Message Queue)에 주로 쓰임
  - BFS(너비 우선 탐색), 다익스트라-우선순위 큐에 활용
  - 파이썬 리스트(list)로 간편하게 사용 가능
    - .append(): 리스트의 끝에 항목을 더함
    - .pop(0): 리스트의 첫 번째 항목을 삭제하고 돌려줌
      - **데이터를 뺄 때 큐 안에 있는 데이터가 많은 경우 비효율적**
      - 맨 앞 데이터가 빠지면서 리스트의 인덱스가 하나씩 당겨지기 때문
  - 덱(Deque, Double-Ended Queue)
    - 양방향으로 삽입과 삭제가 자유로운 큐
    - 덱은 양방향 삽입, 추출이 모두 큐보다 훨씬 빠르기 때문에 데이터의 삽입, 추출이 많을 경우 시간을 크게 단축할 수 있음
- 힙(Heap)
  - 우선순위 큐(Priority Queue)를 구현하는 방법 중 하나
    > 우선순위 큐(Priority Queue)는 우선순위(중요도, 크기 등 순서 이외의 기준)를 기준으로 가장 우선순위가 높은 데이터가 가장 먼저 나가는 방식
  - 최댓값 또는 최솟값을 빠르게 찾아내도록 만들어진 데이터 구조
  - 완전 이진 트리의 형태로 **느슨한 정렬 상태를 지속적으로 유지**함
  - 힙 트리에서는 중복 값을 허용
  - 데이터가 지속적으로 정렬되어야 하는 경우, 데이터에 삽입/삭제가 빈번할 때 사용
  - 파이썬의 heapq 모듈
    - Minheap(최소 힙)으로 구현되어 있음(가장 작은 값이 먼저 나옴)
      - Maxheap(최대 힙)을 구현하기 위해서는 추가 및 출력시 값에 '-'를 붙이면 됨
    - 삽입, 삭제, 수정, 조회 **연산의 속도가 리스트보다 빠름**
    - heapq.heapify(): 리스트를 제자리에서 힙으로 변환함
    - heapq.heappop(heap): 힙 불변성을 유지하면서 heap에서 가장 작은 항목을 삭제하고 반환함
    - heapq.heappush(heap, item): 힙 불변성을 유지하면서 item 값을 heap으로 추가함
- 셋(Set)
  - 수학에서의 '집합'을 나타내는 데이터 구조
  - 파이썬에서 기본적으로 제공되는 데이터 구조
  - 데이터의 중복이 없어야 할 때, 정수가 아닌 데이터의 삽입/삭제/탐색이 빈번히 필요할 때 사용
  - 연산
    - .add(): 원소를 집합에 추가
    - .remove(): 원소를 집합에서 제거
    - set **|** other(합): 집합의 모든 원소들을 합함
    - set **-** other(차): 집합에서 other에 있는 원소를 제거
    - set **&** other(교): 집합과 other에 공통으로 포함된 원소들만 남김
    - set **^** other(대칭차): 두 집합 중 어느 한 곳에만 포함된 원소들만 남김

## 💡 이차원 리스트

- 리스트를 원소로 가지는 리스트
- 행렬(matrix)
  ```
  matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
  ]
  ```
- 입력받기

  - 행렬의 크기가 미리 주어지는 경우

    ```
    3 x 3 크기의 입력을 받아보자.

    1 2 3
    4 5 6
    7 8 9
    ```

    ```python
    matrix = []

    for _ in range(3):
      list = list(map(int, input().split()))
      matrix.append(line)
    ```

    ```python
    matrix = [list(map(int, input().split())) for _ in range(3)]
    ```

  - 행렬의 크기가 입력으로 주어지는 경우

    ```
    n x m 크기의 입력을 받아보자

    3 4
    1 2 3 4
    5 6 7 8
    9 0 1 2
    ```

    ```python
    n, m = map(int, input().split())
    matrix = []
    for_ in range(n):
      line = list(map(int, input().split()))
      matrix.append(line)
    ```

    ```python
    n, m = map(int, input().split())
    matrix = [list(map(int, input().split())) for _ in range(n)]
    ```

- 순회

  - 이중 for문을 이용한 행 우선 순회

    ```python
    matrix = [
      [1, 2, 3, 4],
      [5, 6, 7, 8],
      [9, 0, 1, 2]
    ]

    for i in range(3): # 행
      for j in range(4): # 열
        print(matrix[i][j], end=' ')
      print()
    ```

    ```
    1 2 3 4
    5 6 7 8
    9 0 1 2
    ```

  - 이중 for문을 이용한 열 우선 순회

    ```python
    matrix = [
      [1, 2, 3, 4],
      [5, 6, 7, 8],
      [9, 0, 1, 2]
    ]

    for i in range(4): # 열
      for j in range(3): # 행
        print(matrix[j][i], end=' ')
      print()
    ```

    ```
    1 5 9
    2 6 0
    3 7 1
    4 8 2
    ```

  - 이차원 리스트의 총합 구하기

    - 행 우선 순회를 이용

      ```python
      matrix = [
        [1, 1, 1, 1],
        [1, 1, 1, 1],
        [1, 1, 1, 1]
      ]

      total = 0

      for i in range(3):
        for j in range(4):
          total += matrix[i][j]

      print(total) # 12
      ```

    - pythonic한 방법 이용

      ```python
      matrix = [
        [1, 1, 1, 1],
        [1, 1, 1, 1],
        [1, 1, 1, 1]
      ]

      total = sum(map(sum, matrix))

      print(total) # 12
      ```

  - 이차원 리스트의 최댓값, 최솟값 구하기

    - 행 우선 순회를 이용

      ```python
      matrix = [
        [0, 5, 3, 1],
        [4, 6, 10, 8],
        [9, -1, 1, 5]
      ]

      max_value = 0
      min_value = 99999999

      # 최댓값
      for i in range(3):
        for j in range(4):
          if matrix[i][j] > max_value:
            max_value = matrix[i][j]

      print(max_value) # 10

      # 최솟값
      for i in range(3):
        for j in range(4):
          if matrix[i][j] < min_value:
            min_value = matrix[i][j]

      print(min_value) # -1
      ```

    - pythonic한 방법 이용

      ```python
      matrix = [
        [0, 5, 3, 1],
        [4, 6, 10, 8],
        [9, -1, 1, 5]
      ]

      max_value = max(map(max, matrix))
      min_value = min(map(min, matrix))

      print(max_value) # 10
      print(min_value) # -1
      ```

  - 전치

    - 전치(transpose)란 행렬의 행과 열을 서로 맞바꾸는 것을 의미

    ```python
    matrix = [
      [1, 2, 3, 4],
      [5, 6, 7, 8],
      [9, 0, 1, 2]
    ]

    transposed_matrix = [[0] * 3 for _ in range(4)]

    for i in range(4):
      for j in range(3):
        transposed_matrix[i][j] = matrix[j][i] # 행, 열 맞바꾸기
    ```

    ```
    transposed_matrix = [
      [1, 5, 9],
      [2, 6, 0],
      [3, 7, 1],
      [4, 8, 2]
    ]
    ```

  - 회전

    - 왼쪽으로 90도 회전하기

      ```python
      matrix = [
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
      ]

      n = 3
      rotated_matrix = [[0] * n for _ in range(n)]

      for i in range(n):
        for j in range(n):
          rotated_matrix[i][j] = matrix[j][n-i-1]
      ```

      ```
      rotated_matrix = [
        [3, 6, 9],
        [2, 5, 8],
        [1, 4, 7]
      ]
      ```

    - 오른쪽으로 90도 회전하기

      ```python
      matrix = [
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
      ]

      n = 3
      rotated_matrix = [[0] * n for _ in range(n)]

      for i in range(n):
        for j in range(n):
          rotated_matrix[i][j] = matrix[n-j-1][i]
      ```

      ```
      rotated_matrix = [
        [7, 4, 1],
        [8, 5, 2],
        [9, 6, 3]
      ]
      ```

## 💡 완전 탐색(Exhaustive Search)

- 무식하게 풀기(Brute-force)

  - Brute-force는 **모든 경우의 수**를 탐색하여 문제를 해결하는 방식
  - 가장 단순한 풀이 기법이며 단순 조건문과 반복문을 이용
  - 복잡한 알고리즘보다는 아이디어를 어떻게 코드로 구현할 것인지가 중요
  - 예시 문제: [BOJ 2798 블랙잭](https://www.acmicpc.net/problem/2798)

    ```python
    def blackjack(n, m, cards):
      max_total = 0 # 현재 가장 큰 합

      # 완전 탐색(Brute-force)
      for i in range(n-2):
        for j in range(i+1, n-1):
          for k in range(j+1, n):
            total = cards[i] + cards[j] + cards[k]

            # 현재 가장 큰 합보다는 크고, m을 넘지 않아야 갱신
            if max_total < total <= m:
              max_total = total

            # 합과 m이 같으면 더 이상 탐색하는 의미가 없으므로 종료
            if total == m:
              return total

      return max_total
    ```

- 델타 탐색(Delta Search)

  - **델타 탐색(상하좌우 탐색)**은 **이차원 리스트의 완전 탐색**에서 많이 등장하는 유형
  - (0, 0)에서부터 이차원 리스트의 모든 원소를 순회하며 **각 지점에서 상하좌우에 위치한 다른 지점을 조회하거나 이동**하는 방식
  - 이차원 리스트의 인덱스(좌표)의 조작을 통해 상하좌우 탐색을 하는데 이때 행과 열의 변량인 -1, +1을 **델타(delta)값**이라 함
  - 이차원 리스트의 상하좌우 탐색

    ```python
    # (1) 델타값 정의(상하좌우)
    dx = [-1, 1, 0, 0]
    dy = [0, 0, -1, 1]

    # (2) 이차원 리스트 순회
    for x in range(n):
      for y in range(m):

        # (3) 델타값을 이용해 상하좌우 이동
        for i in range(4):
          nx = x + dx[i]
          ny = y + dy[i]

          # (4) 범위를 벗어나지 않으면 갱신
          if 0 <= nx < n and 0 <= ny < m:
            x = nx
            y = ny
    ```

## 💡 그래프(Graph)

- 정점(Vertex)과 이를 연결하는 간선(Edge)들의 집합으로 이루어진 비선형 자료구조
  - 정점(Vertex): 간선으로 연결되는 객체이며, 노드(Node)라고도 함
  - 간선(Edge): 정점 간의 관계(연결)를 표현하는 선
  - 경로(Path): 시작 정점부터 도착 정점까지 거치는 정점을 나열한 것
  - 인접(Adjacency): 두 개의 정점이 하나의 간선으로 직접 연결된 상태
- 그래프의 종류
  - 무방향 그래프(Undirected graph)
    - 간선의 방향이 없는 가장 일반적인 그래프
    - 간선을 통해 양방향의 정점 이동 가능
    - 차수(Degree): 하나의 정점에 연결된 간선의 개수
    - 모든 정점의 차수의 합 = 간선 수 \* 2
  - 유방향 그래프(Directed graph)
    - 간선의 방향이 있는 그래프
    - 간선의 방향이 가리키는 정점으로 이동 가능
    - 차수(Degree): 진입 차수와 진출 차수로 나누어짐
      - 진입 차수(In-degree): 외부 정점에서 한 정점으로 들어오는 간선의 수
      - 진출 차수(Out-degree): 한 정점에서 외부 정점으로 나가는 간선의 수
- 그래프의 표현

  - 인접 행렬(Adjacent matrix)

    - 두 정점을 연결하는 간선이 없으면 0, 있으면 1을 가지는 행렬로 표현하는 방식
    - 인접 행렬은 직관적이고 만들기 편하지만 불필요하게 공간이 낭비됨

      ```python
      # 입력

       0 1
       0 2
       1 3
       1 4
       2 4
       2 5
       4 6
      ```

      ```python
      # 인접 행렬 만들기

      n = 7 # 정점 개수
      m = 7 # 간선 개수

      graph = [[0 * n for _ in range(n)]]

      for _ in range(m):
        v1, v2 = map(int, input().split())
        graph[v1][v2] = 1
        graph[v2][v1] = 1
      ```

      ```python
      # 인접 행렬 결과

      graph = [
        [0, 1, 1, 0, 0, 0, 0],
        [1, 0, 0, 1, 1, 0, 0],
        [1, 0, 0, 0, 1, 1, 0],
        [0, 1, 0, 0, 0, 0, 0],
        [0, 1, 1, 0, 0, 0, 1],
        [0, 0, 1, 0, 0, 0, 0],
        [0, 0, 0, 0, 1, 0, 0]
      ]
      ```

  - 인접 리스트(Adjacent list)

    - 리스트를 통해 각 정점에 대한 인접 정점들을 순차적으로 표현하는 방식
    - 인접 리스트는 연결된 정점만 저장하여 효율적이므로 자주 사용됨

      ```python
      # 입력

       0 1
       0 2
       1 3
       1 4
       2 4
       2 5
       4 6
      ```

      ```python
      # 인접 리스트 만들기

      n = 7 # 정점 개수
      m = 7 # 간선 개수

      graph = [[] for _ in range(n)]

      for _ in range(m):
        v1, v2 = map(int, input().split())
        graph[v1].append(v2)
        graph[v2].append(v1)
      ```

      ```python
      # 인접 리스트 결과

      graph = [
        [1, 2],
        [0, 3, 4],
        [0, 4, 5],
        [1],
        [1, 2, 6],
        [2],
        [4]
      ]
      ```

## 💡 깊이우선탐색(DFS)

- 시작 정점으로부터 **갈 수 있는 하위 정점까지 가장 깊게 탐색**하고 더 이상 갈 곳이 없다면 마지막 갈림길로 돌아와서 다른 정점을 탐색하며 결국 모든 정점을 방문하는 순회 방법
- 미로 탈출로 생각하면 쉬움. **어느 한쪽 길로 가장 깊게 들어갔다가 막히면 다시 돌아와서 다른 길을 탐색**함
- **모든 정점을 방문**할 때 유리
- **경우의 수, 순열과 조합** 문제에서 많이 사용
- 너비우선탐색(BFS)에 비해 코드 구현이 간단함
- 단, 모든 정점을 방문할 필요가 없거나 최단 거리를 구하는 경우에는 너비우선탐색(BFS)이 유리함
- DFS의 동작 과정
  - DFS를 하기 전에 일단 탐색을 진행할 그래프가 필요함
    - 그래프는 **인접 행렬** 혹은 **인접 리스트** 방식으로 표현 가능
  - **각 정점을 방문했는지 여부를 판별**할 방문 체크 리스트가 필요함
    - visited 리스트를 따로 선언하여 각 정점을 방문했는지 체크
  - DFS의 사이클
    1. 정점 방문 처리 및 스택에 값 삽입
    2. 스택 마지막 값 꺼내고 인접한 정점 확인
    3. 방문하지 않은 인접 정점
    4. 다시 1번부터 과정 반복
- DFS 대표 예제: [BOJ 2606 바이러스](https://www.acmicpc.net/problem/2606)

  ```python
  N = int(input()) # 정점 개수(컴퓨터)
  M = int(input()) # 간선 개수(네트워크)

  graph = [[] for _ in range(N + 1)]
  visited = [False] * (N + 1)
  cnt = 0

  # 인접 리스트 만들기
  for _ in range(M):
    v1, v2 = map(int, input().split())
    graph[v1].append(v2)
    graph[v2].append(v1)

  start = 1 # 1번 정점(컴퓨터)에서 시작
  stack = [start]
  visited[start] = True # 스택에 정점 추가 및 방문 처리

  while stack:
    cur = stack.pop() # 스택에서 탐색 정점 꺼내기

    for adj in graph[cur]: # 현재 탐색 정점의 인접 정점 확인
      if not visited[adj]:
        visited[adj] = True
        stack.append(adj) # 미방문 정점 스택에 추가 및 방문 처리
        cnt += 1

  print(cnt)
  ```
