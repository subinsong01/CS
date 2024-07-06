# 📕 탐색 알고리즘 BFS & DFS 

## DFS(Depth First Search) -> stack으로 구현한다 (재귀함수)

➡️ **깊이 우선 탐색**이라고 부르며, 그래프에서 깊은 부분을 우선적으로 탐색하는 알고리즘 </br>

<img width="355" alt="스크린샷 2024-07-06 오후 4 26 01" src="https://github.com/subinsong01/TIL/assets/134045937/234ff13a-41fe-4feb-a145-44a54bf03135">

> 한 놈만 팬다 느낌,,(?)

### - 인접 행렬 : 2차원 배열로 그래프의 연결 관계를 표현하는 방식
### - 인접 리스트 : 리스트로 그래프의 연결 관계를 표현하는 방식

두 가지 방식으로 표현이 가능하다. 

➡️ **인접행렬**에 대해서 더 깊이 있게 설명하자면, 이는 2차원 배열에 각 노드가 연결된 형태를 기록하는 방식이며, 2차원 리스트로 구현이 가능하다 
➡️ 연결이 되어 있지 않은 노드끼리는 무한의 비용이라고 작성핝다. 

<img width="554" alt="스크린샷 2024-07-06 오후 4 37 48" src="https://github.com/subinsong01/TIL/assets/134045937/500be398-1463-41f6-b5d1-2893e6a72f7c">

```py
#인접 행렬 방식

INF = 99999999 #무한 비용의 선언

# 2차원 리스트를 이용해 인접 행렬 표현
graph = [
  [0, 7, 5],
  [7, 0, INF],
  [5, INF, 0]
]
print(graph)
```
```py
출력 : [[0,7,5], [7,0,99999999], [5,99999999,0]]
```

➡️ **인접 리스트 방식**은 데이터를 모든 노드에 연결된 노드에 대한 정보를 차례대로 연결하여 저장한다.

<img width="583" alt="스크린샷 2024-07-06 오후 4 39 27" src="https://github.com/subinsong01/TIL/assets/134045937/be36f916-7b7b-4bb8-b5ea-9cb00e05f9b9">

```py
#행이 3개인 2차원 리스트로 인접 리스트 표현

graph = [[] for _ in range(3)]

# 노트 0에 연결된 노드 정보 저장(노드, 거리)
graph[0].append((1, 7))
graph[0].append((2, 5))

# 노트 1에 연결된 노드 정보 저장(노드, 거리)
graph[1].append((0, 7))

# 노트 2에 연결된 노드 정보 저장(노드, 거리)
graph[2].append((0, 5))

print(graph)
```
```py
출력 : [[(1,7), (2,,5)], [(0,7)], [(0,5)]]
```
## 어떤게 더 효율적일까 ? 🤔
➡️  `인접 리스트`는 연결된 정보만을 저장하기 때문에 `인접 행렬`보다 더 효율적으로 메모리 사용이 가능하다 
### 하지만
➡️ `인접 리스트` 방식은 `인접 행렬`보다 느리다는 특징이 있다. 

```py
#DFS 메서드 정의
def dfs(graph, v, visited):
  #현재 노드를 방문 처리
  visited[v] = True
  print(v, end= '')
  #현재 노드와 연결된 다른 노드를 재귀적으로 방문
  for i in graph[v]:
    if not visited[i]:
      dfs(graph, i, visited)

#각 노드가 연결된 정보를 리스트 자료형으로 표현(2차원 리스트)
graph = [
  [],
  [2, 3, 8],
  [1,7],
  [1,4,5],
  [3,5],
  [3,4],
  [7],
  [2,6,8],
  [1,7]
]

#각 노드가 방문된 정보를 리스트 자료형으로 표현(1차원 리스트)
visited = [False] * 9

#정의된 DFS 함수 호출
dfs(graph, 1, visited)
```
```py
출력 : 1 2 7 6 8 3 4 5
```
-----------------

## BFS(Breadth First Search) -> queue로 구현한다 

➡️ **너비 우선 탐색**이라고 부르며, 그래프에서 가까운 부분을 우선적으로 탐색하는 알고리즘 </br>

<img width="331" alt="스크린샷 2024-07-06 오후 4 44 36" src="https://github.com/subinsong01/TIL/assets/134045937/3559f15c-0301-4afb-b85d-a91e267ea0fa">

### - deque 라이브러리를 활용한다 ➡️ O(N)의 시간이 소요된다 
### - 일반적으로 DFS 보다 수행시간이 좋다. 

```py
#BFS 예제

from collections import deque

# BFS 메서드 정리
def bfs(graph, start, visited):
  #큐(Queue) 구현을 위해서 deque 라이브러리 사용
  queue = deque([start])
  #현재 노드를 방문 처리
  visited[start] = True
  #큐가 빌 때까지 반복
  while queue:
    #큐에서 하나의 원소를 뽑아 출력
    v = queue.popleft()
    print(v, end='')
    # 해당 원소와 연결된, 아직 방문하지 않은 원소들을 큐에 삽입
    for i in graph[v]:
      if not visited[i]:
        queue.append(i)
        visited[i] = True


#각 노드가 연결된 정보를 리스트 자료형으로 표현(2차원 리스트)
graph = [
  [],
  [2, 3, 8],
  [1,7],
  [1,4,5],
  [3,5],
  [3,4],
  [7],
  [2,6,8],
  [1,7]
]

#각 노드가 방문된 정보를 리스트 자료형으로 표현(1차원 리스트)
visited = [False] * 9

#정의된 BFS 함수 호출
bfs(graph, 1, visited)

```py
출력 : 1 2 3 8 7 4 5 6 
```


