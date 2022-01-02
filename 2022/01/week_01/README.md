## 01월 01일

> 새해니까 가볍게 손 풀기😄

##### 1. 한 단위로 바꾸기

```python
total_minute = hour * 60 + minute # 분 단위로 바꿈
```

##### 2. 구하고 싶은 시간 = 입력 받은 시간 - 45분

```python
total_minute -= 45 # 원하는 시간 = total_minute - 45
```

##### 3. 다시 시간 단위 바꾸기

```python
result_hour = total_minute // 60 % 24 # 원하는 hour = 전체 시간을 60으로 나눈 몫 mod 24
result_minute = total_minute % 60 # 원하는 hour = (전체 시간) mod 60
```

---

## 01월 02일

> 백트래킹은 왤케 어려운걸까.. 아무리 풀어도 어렵네😂

##### 1. 반복문 돌면서 재귀 호출하기

```python
for i in range(start, N + 1):
    stack.append(i)
    solution(i)
    stack.pop()
```

- `stack.append(i)`: `stack`에 `i` `push`
  - 예시: `[1]` ➜ `[1, 1]`
- `stack.pop()`: 앞에서 넣어준 `i` `pop`
  - 예시: `[1, 1]` ➜ `[1]`

##### 2. 조건 만족하면 출력하고 종료

```python
if len(stack) == M:
    print(*stack)
    return
```

---
