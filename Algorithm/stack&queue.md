# 📘 stack & queue -> BFS & DFS 

### BFS&DFS를 공부하기 이전에 알아야할 자료구조 내용
> stack & queue

✏️ stack(FILO) </br>

` 가장 먼저 들어간 것이 가장 나중에 나오는 형식을 말한다.`

<img width="300" alt="스크린샷 2024-06-30 오후 1 59 54" src="https://github.com/subinsong01/TIL/assets/134045937/09554d8d-27e7-4ca1-8a1b-e168350bb7f0">

- 데이터 삽입 : push
- 데이터 삭제 : pop
- 시간 복잡도 O(1)
  
EX)  #삽입(5)-삽입(2)-삽입(3)-삽입(7)-삭제()-삽입(1)-삽입(4)-삭제()</br>

```py
stack = []
stack.append(5)
stack.append(2)
stack.append(3)
stack.append(7)
stack.pop()
stack.append(1)
stack.append(4)
stack.pop()

print(stack) #최하단 원소부터 출력
print(stack[::-1]) #최상단 원소부터 출력
```
```
출력
[5,2,3,1]
[1,3,2,5]
```

✏️ queue(FIFO) </br>

` 가장 먼저 들어간 것이 가장 먼저 나오는 형식을 말한다.`

<img width="300" alt="스크린샷 2024-06-30 오후 3 54 59" src="https://github.com/subinsong01/TIL/assets/134045937/01dc0a32-4d2b-44c0-9401-091163c9a53c">


- 큐 맨 뒤에 데이터 추가 : Enqueue
- 큐 맨 앞쪽의 데이터 삭제 :  Dequeue

EX)  #삽입(5)-삽입(2)-삽입(3)-삽입(7)-삭제()-삽입(1)-삽입(4)-삭제()</br>

```py
from collections import deque 

queue = deque() #큐(Queue) 구현을 위해서 deque 라이브러리 사용

queue.append(5)
queue.append(2)
queue.append(3)
queue.append(7)
queue.popleft(7)
queue.append(1)
queue.append(4)
queue.popleft()

print(queue) #먼저 들어온 순서대로 출력
queue.reverse() # 역순으로 바꾸기
print(queue) #나중에 들어온 순서대로 출력
```
```
출력
deque([3,7,1,4])
deque([4,1,7,3])
```
> reference : 이것이 취업을 위한 코딩테스트다
