# 그리디 (22.03.29)

## 그리디 알고리즘이란?

- 단순하지만 강력한 문제 해결 방법
- 어떤 문제가 있을 때, 단순 무식하게, 탐욕적으로 문제를 푸는 방법
- **현재 상황에서 지금 당장 좋은 것만 고르는 방법**
- 매 순간 가장 좋아 보이는 것만을 선택하며, 현재의 선택이 나중에 미칠 영향에 대해서는 고려하지 않는다.

## 풀이 전략

- 사전에 외우고 있지 않아도 풀 수 있을 가능성이 높은 문제 유형
- 문제 출제의 폭이 매우 넓다.
- 많은 유형을 접해보고 문제를 풀어보며 훈련해야 한다.
- 창의력을 요구하는 문제들이 많음
- '가장 큰 순서대로', '가장 작은 순서대로'와 같은 기준을 제시해준다.

> **특정한 문제를 만났을 때 단순히 현재 상황에서 가장 좋아 보이는 것만을 선택해도 문제를 풀 수 있는지를 파악할 수 있어야 한다.**

## 예제 풀이

### 예제 코드

```python
# 예제 3-1 거스름돈

import sys

n = int(sys.stdin.readline())
coinList = [500, 100, 50, 10]
result = 0

for coin in coinList:
  result += n // coin
  n %= coin

print(result)
```

### 코드 해설

- 동전의 **최소** 개수를 요구하기 때문에 큰 금액부터 순서대로 리스트에 저장한다.
- 동전의 개수를 세어줄 변수 **result**를 0으로 초기화한다.
- 리스트를 순회하며 총액을 금액으로 나눈 몫을 **result**에 저장한다.
- 나머지는 총액 **n**에 저장하고 다음 동전으로 넘어간다.
- 반복한다.

### 시간 복잡도

- 동전의 개수가 K개라고 할 때, K번 탐색하므로 시간 복잡도는 O(K)이다.
- 시간 복잡도는 동전의 총 종류에만 영향을 받고, 총액에는 영향을 받지 않는다.

## 그리디 알고리즘의 정당성

- 탐욕적으로 문제에 접근했을 때 정확한 답을 찾을 수 있다는 보장이 있을 때는 매우 효과적이고 직관적
- 그리디 알고리즘으로 문제의 해법을 찾았을 때는 그 해법이 정당한지 검토해야 한다.
- 가지고 있는 동전 중에서 큰 단위가 항상 작은 단위의 배수이므로 작은 단위의 동전들을 종합해 다른 해가 나올 수 없기 때문이다.
- '가장 큰 단위의 화폐부터 가장 작은 단위의 화폐까지 차례대로 확인하여 거슬러 주는 작업만을 수행하면 된다'는 아이디어는 정당
- **대부분의 그리디 알고리즘 문제에서는 이처럼 문제 풀이를 위한 최소한의 아이디어를 떠올리고 이것이 정당한지 검토할 수 있어야 답을 도출할 수 있다.**

## 결론

- 문제를 딱 보고 뭔지 모르겠으면 그리디 알고리즘을 의심해본다.
- 동전이 배수 형태가 아니라 무작위로 주어진다면 그리디가 아니고 DP
- 연습문제들을 30분 이내에 풀 수 있어야함

## 예제

**프로그래머스 Level1 - 체육복**
![예제](../../img/스크린샷%202022-04-08%20오후%209.04.40.png)
https://programmers.co.kr/learn/courses/30/lessons/42862?language=python3

### 문제 설명

점심시간에 도둑이 들어, 일부 학생이 체육복을 도난당했습니다. 다행히 여벌 체육복이 있는 학생이 이들에게 체육복을 빌려주려 합니다. 학생들의 번호는 체격 순으로 매겨져 있어, 바로 앞번호의 학생이나 바로 뒷번호의 학생에게만 체육복을 빌려줄 수 있습니다. 예를 들어, 4번 학생은 3번 학생이나 5번 학생에게만 체육복을 빌려줄 수 있습니다. 체육복이 없으면 수업을 들을 수 없기 때문에 체육복을 적절히 빌려 최대한 많은 학생이 체육수업을 들어야 합니다.

전체 학생의 수 n, 체육복을 도난당한 학생들의 번호가 담긴 배열 lost, 여벌의 체육복을 가져온 학생들의 번호가 담긴 배열 reserve가 매개변수로 주어질 때, 체육수업을 들을 수 있는 학생의 최댓값을 return 하도록 solution 함수를 작성해주세요.

> **요약**
>
> 1. 학생들의 번호는 체격 순으로 매겨져 있다.
> 2. 최대한 많은 학생이 체육복을 입고 수업을 들어야 한다.

**제한사항**

- 전체 학생 수는 2명 이상 30명 이하이다.
- 체육복을 도난당한 학생의 수는 1명 이상 n명 이하이고 중복되는 번호는 없다.
- 여별의 체육복을 가져온 학생의 수는 1명 이상 n명 이하이고 중복되는 번호는 없다.
- 여별 체육복이 있는 학생만 다른 학생에게 체육복을 빌려줄 수 있다.
- 여별 체육복을 가져온 학생이 체육복을 도난당했을 수 있다. 이 때 이 학생은 체육복을 하나만 도난당했다고 가정하며, 남은 체육복이 하나이기에 다른 학생에게는 체육복을 빌려줄 수 없다.

**입출력 예**
|n|lost|reserve|return|
|--|---|-------|------|
|5|[2, 4]|[1, 3, 5]|5|
|5|[2, 4]|[3]|4|
|3|[3]|[1]|2|

**입출력 예 설명**  
예제 #1  
1번 학생이 2번 학생에게 체육복을 빌려주고, 3번 학생이나 5번 학생이 4번 학생에게 체육복을 빌려주면 학생 5명이 체육수업을 들을 수 있습니다.

예제 #2
3번 학생이 2번 학생이나 4번 학생에게 체육복을 빌려주면 학생 4명이 체육수업을 들을 수 있습니다.

**예상 시간복잡도**
n개의 리스트를 탐색해야 할 것이므로 **O(n)** 이 나올 것으로 예상된다.

```python
def solution(n, lost, reserve):
    set_lost = set(lost) - set(reserve)
    set_reserve = set(reserve) - set(lost)

    for l in set_lost:
      a = l - 1
      b = l + 1

      if a in set_reserve:
        set_reserve.remove(a)
      elif b in _reserve:
        set_reserve.remove(b)
      else:
        n -= 1

    answer = n
    return answer
```

![solution](../../img/스크린샷%202022-04-08%20오후%2011.29.30.png)

### 풀이 해설

- 문제를 읽을 때 유의해야 할 점은 **여분의 체육복을 가지고 있는 학생의 체육복이 도둑맞을 수도 있다는 점**이다.
- 이 문제를 해결하기 위해 차집합을 사용하여 lost와 reserve 간의 중복을 제거해 주었다.
- 맨 첫 단계에서 최적의 해는 **1번이 2번에게 체육복을 빌려주는 경우의 수**라고 판단하여 앞 번호에서 뒷 번호로 체육복을 빌려주는 방법을 채택하였다.
- a라는 변수를 할당하여 **lost+1** 값이 set_reserve 리스트에 있는지 확인하였고, 있다면 set_reserve 리스트에서 제거하는 방법으로 여러번 체육복을 빌려주는 경우를 배제하였다.
- 차선으로 b라는 변수를 할당하였고 **lost-1** 값이 set_reserve 리스트에 있는지 확인하였고, 마찬가지로 set_reserve 리스트에서 제거해주었다.
- 이 두가지 경우의 수 모두에 해당하지 않는 경우 체육복을 빌릴 수 없다는 의미이므로 n에서 1을 빼 주었다.
- 시간복잡도는 반복문에서 set_lost를 모두 탐색하는 비용 O(set_lost) +  
  조건문에서 set_reserve를 탐색하는 비용 O(set_reserve) 이므로 **O(set_lost + set_reserve)**임을 알 수 있다.
- 결과적으로 예상했던 O(n)보다 저렴하거나 같은 비용의 알고리즘임을 알 수 있다.
