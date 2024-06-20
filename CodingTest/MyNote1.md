# 👻 Essential Grammer to solve CodingTest(Python)

## CH01. 자료형

1. 자료형
   
-  리스트 컴프리헨션 : 리스트를 초기화하는 방법 중 하나이다.
  
```py
# 0부터 19까지의 수 중에서 홀수만 포함하는 리스트
array = [ i for i in range(20) if i % 2 == 1]
print(array)

=> [1,3,5,7,9,11,13,15,17,19]
```
```py
#N X M 크기의 2차원 리스트 초기화
n = 3
m = 4
array = [[0] * m for _in range(n)]
print(array)

=> [[0,0,0,0], [0,0,0,0], [0,0,0,0]]
```
⭐️ 여기서 언더바(_)가 어떤 역할인가 
- 반복을 수행하되 반복을 위한 변수의 값을 무시하고자 할 때 언더바를 사용한다.
  
ex) 
```py
summary = 0

for i in range(1, 10):
  summary += i
print(summary)
```
```py
for _ in range(5):
  print("Hello World!")
```
| append()  | sort() | reverse() | insert() |
| - | - | - | - |
| 변수명.append() | 변수명.sort() / 변수명.sort(reverse=True) | 변수명.reverse() | insert(삽입할 위치 인덱스, 삽입할 값) |
| 리스트에 원소를 하나 삽입할 대 사용한다 | 기본 정렬 기능으로, 오름차순으로 정렬  | 리스트의 원소의 순서를 모두 뒤집어 놓는다 | 특정한 인덱스 위치에 원소를 삽입할 때 사용 |

| count | remove | 
| - | - | 
| 변수명.count(특정 값) | 변수명.remove(특정 값)| 
| 리스트에서 특정한 값을 가지는 데이터의 개수를 셀 때 사용한다 | 특정한 값을 갖는 원소를 제거하는데, 값을 가진 원소가 여러 개면 하나만 제거한다. | 

2. 튜플 (💡그래프 알고리즘에서 많이 사용💡)
   
   - 튜플은 리스트랑 다르게 한 번 선언하면 변경이 불가능하다
   - 리스트는 [] / 튜플은 () 사용

3. 사전 자료형 : 키와 값을 쌍으로 가지는 데이터 => dict()

```py
data = dict()
data['사과'] = 'Apple'
data['바나나'] = 'Banana'
data['오렌지'] = 'Orange'

print(data)

=> ['사과' : 'Apple', '바나나' : 'Banana', '오렌지' : 'Orange']
```
4. 집합 자료형 (set)
   
- 중복을 허용하지 않는다 
- 순서가 없다
  
```py
#집합 자료형 초기화 방법1
data = set([1,1,1,2,3,4,4,5])
print(data)

#집합 자료형 초기화 방법2
data (1,1,2,2,3,4,5)
print(data)

=> {1,2,3,4,5}
=> {1,2,3,4,5}
```

5. 집합 자료형 관련 함수

- add() : 집합 데이터에 값을 추가할 때 사용
- update() : 여러 개의 값을 한번에 추가하고자 할 때 사용
- remove() : 특정 값을 제거할 때 사용 
