# 투 포인터(Two Pointer)
### 리스트에 순차적으로 접근해야 할 때 두 개의 점의 위치를 기록하면서 처리하는 알고리즘을 의미한다. 
✏️ 2, 3, 4, 5, 6, 7번 학생을 지목해야 할 때 간단히 2번부터 7번까지의 학생이라고 부르는데, 
리스트에 담긴 데이터에 순차적으로 접근해야 할 때는 시작점과 끝점 2개의 점으로 접근할 데이터의 범위를 표현할 수 있다.<br>
✏️ 연속하다는 특성을 이용해서 처리한다.  <br>
### 📍 즉, 리스트에 순차적으로 접근해야 할 때 2개의 점의 위치를 기록하면서 처리하는 알고리즘을 의미한다.
> 백준 2559
```py
import sys
input = sys.stdin.readline

N, K = map(int, input().split())
nums = list(map(int, input().split()))
each = 0 

for i in range(K):
    each += nums[i]
max_value = each 

for i in range(K, N):
    each += nums[i]
    each -= nums[i-k]
    max_value = max(max_value, each)
    
print(max_value)
```
> 백준 20922
```py
import sys
input = sys.stdin.readline

N, K = map(int, input().split()) #K가 기준 
each = list(map(int, input().split()))

left, right = 0, 0
answer = 0

cnt = [0] * (max(each)+1)

while right < N:
    if cnt[each[right]] < K:
        cnt[each[right]] += 1
        right += 1
    else:
        cnt[each[left]] -= 1
        left += 1
    answer = max(answer, right-left)

print(answer)
```

- 투포인터 알고리즘의 특징은 2개의 변수를 이용해 리스트 상의 위치를 기록한다는 점이다.대부분의 문제에서는 부분 연속 수열의 시작점(start)과 끝점(end)의 위치를 기록한다.
- 특정한 부분합을 M이라고 할 때, 구체적인 알고리즘은 다음과 같다.
1. 시작점(start)과 끝점(end)이 첫 번째 원소의 인덱스(0)을 가리키도록 한다.
2. 현재 부분합이 M과 같다면 카운트 한다.
3. 현재 부분합이 M보다 작으면 end를 1 증가시킨다.
4. 현재 부분합이 M보다 크거나 같으면 start를 1 증가시킨다.
5. 모든 경우를 확인할 때까지 2번부터 4번까지의 과정을 반복한다.


출처 : https://velog.io/@mjieun/Algorithm-%ED%88%AC-%ED%8F%AC%EC%9D%B8%ED%84%B0Two-Pointers-Python#:~:text=%ED%88%AC%20%ED%8F%AC%EC%9D%B8%ED%84%B0(Two%20Pointers)%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98%EC%9D%80%20%EB%A6%AC%EC%8A%A4%ED%8A%B8%EC%97%90%20%EC%88%9C%EC%B0%A8%EC%A0%81%EC%9C%BC%EB%A1%9C,%ED%95%A0%20%EA%B2%BD%EC%9A%B0%EB%A5%BC%20%EC%83%9D%EA%B0%81%ED%95%B4%EB%B3%B4%EC%9E%90.
