# 3주차

> - string
> - hash
> - sort

---

## 21.07.19 - string

> - [1269 - 대칭 차집합](https://www.acmicpc.net/problem/1269)
> - [1316 - 그룹 단어 체커](https://www.acmicpc.net/problem/1316)
> - [1541 - 잃어버린 괄호](https://www.acmicpc.net/problem/1541)
> - [1544 - 사이클 단어](https://www.acmicpc.net/problem/1544)
> - [1764 - 듣보잡](https://www.acmicpc.net/problem/1764)
> - [2577 - 숫자의 개수](https://www.acmicpc.net/problem/2577)
> - [2751 - 수 정렬하기2](https://www.acmicpc.net/problem/2751)

`<1269>`

저번에 프로그래머스 풀 때 counter모듈 썻던 기억이 있어서 바로 이용해봤다.

```python
A = Counter([1, 2, 3, 4, 5])
print(A)
#{1: 1, 2: 1, 3: 1, 4: 1, 5: 1}
```

counter를 이용하면 이렇게 된다.

차집합도 쉽게 구해진다 ~.

`<1316>`

이 문제는 dict 자료형을 사용했다. 사실 투머치같다고 생각이 드는데 그냥 보자마자 든 생각이 dict이어서 일단 실행에 옮겼다.

1. 처음 나오는 알파벳이면 {'알파벳' : True}를 추가해준다.
2. 만약에 알파벳이 이전에 나온 알파벳이고 앞의 알파벳이랑 같다면?(연속된다면) 통과
3. 그런데 이전에 나온 알파벳인데 앞의 알파벳과 연속되지 않는다면? flag를 false로 바꿔주고 뒤를 더 볼 필요가 없으므로 break해준다.
4. flag가 true라면 count를 세주고
5. count 출력

`<1541>`

처음 봤을때 실버 2 문제라길래 겁먹었는데 잠시 생각해보니까 너무 간단한 문제였다.

\- 가 나온 이후론 모든 숫자를 - 붙여서 더해주면 된다.
ex) 55 - 20 + 30 - 39 + 30
=> 55 - (20 + 30) - (39 + 30)
=> 55 - 20 -30 -39 -30
이렇게 처음 - 이후의 숫자들은 모두 음수로 바꿔지고, 결국은 제일 최소의 결과가 된다.

`<1544>`

이번에도 dict 자료형을 사용했다
사이클 문자열인지 보려면 입력받은 문자열을 두번 합쳐서 검사하면 된다.

ex) dict: {'elloh': 1}라고 치고
입력값이 "hello" -> hellohello이고 이때 elloh가 hellohello안에 있는지 검사해주면 된다.

```python
if len(key) == len(data) and (key in data * 2):
```

시간을 조금이라도 줄이려면 입력값과 key의 길이가 같을때 만 비교해주면 된다.!

`<1764>`

여기서도 counter를 활용했다

우선 듣지도 못한 친구들과 보지도 못한 친구들을 counter 모듈로 만들어 주고
둘을 합쳤다..!

듣지도 보지도 못한 친구라면 이름이 2번이나 언급된다. 따라서 조건에 맞는 이름을 정렬해서 출력해주면 된다.

`<2577>`

그냥 문제에서 하라는 대로 하면 성공 !

`<2751>`

그냥 당차게 풀었다가 메모리를 다 써버려서 틀렸다. 그래서 문제에서 10000개 이하의 숫자가 주어진다 해서 그냥 카운터 정렬로 풀었다.
카운터 정렬은 실전에서 처음 써보는데 일정 범위 숫자만 있다면 쓸 수 있겠는데 범위가 너무 넓다면 굳이 안쓰고 싶은? 그런 정렬

---