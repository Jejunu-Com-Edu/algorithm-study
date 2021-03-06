# 구현
###  '머릿속에 있는 알고리즘을 소스코드로 바꾸는 과정'
<br>

## 구현(implementation)이란 ?
- 모든 범위의 코딩 테스트 문제 유형을 포함하는 개념
- 프로그래밍 언어의 문법을 정확히 알고 있어야하고 문제의 요구사항에 어긋나지 않도록 접근
- 구현 유형의 문제는 '풀이를 떠올리는 것은 쉽지만 소스코드로 옮기기 어려운 문제'

  ### 완전탐색
    모든 경우의 수를 주저 없이 다 계산하는 방법
  
  ### 시뮬레이션
    문제에서 제시한 알고리즘을 한 단계씩 차례대로 수행해야하는 문제 유형
     ex) 특정 캐릭터나 어떤 사물등이 특정 위치에 존재했다가 상하좌우 등으로 이동할 수 있다라는 상황이 주어지는 문제 -> 방향벡터

<br>
<br>

## 구현 시 고려해야 할 메모리 제약 상황
- 파이썬은 다른 언어에 비해서 구현상의 복잡함이 적은 편이지만 데이터 처리량이 많을때는 꼭 메모리 제한을 고려해야함
- 대체로 코딩 테스트에서는 128~512MB로 메모리를 제한 

## 채점 환경
- 파이썬은 C/C++에 비해 동작 속도가 느림
- 파이썬은 1초에 2000만 번의 연산을 수행한다고 가정하면 무리는 없음

## 구현 문제에 접근하는 방법
- 고차원적인 사고력을 요구하는 문제는 나오지 않는 편이라 문법에 익숙하면 쉽게 풀 수 있음
- 문자열을 처리하거나 큰 정수를 처리하는 문제가 출제되는 경우가 많음
- 파이썬은 기본 문법만 알아도 상대적으로 구현 유형의 문제를 쉽게 해결 가능

<br>
<br>

## 예제
여행가 A는 N x N 크기의 정사각형 공간 위에 서 있습니다. 이 공간은 1x1 크기의 정사각형으로 나누어져 있습니다. 가장 왼쪽 위 좌표는(1,1)이며, 가장 오른쪽 아래 좌표는 (N,N)에 해당합니다. 여행가 A는 상, 하, 좌, 우 방향으로 이동할 수 있으며, 시작 좌표는 항상 (1,1)입니다. 우리 앞에는 여행가 A가 이동할 계획이 적힌 계획서가 놓여있습니다.

 - 입력조건
 1. 첫째 줄에 공간의 크기를 나타내는 N이 주어집니다.(1 <= N <= 100)
 2. 둘째 줄에 여행가 A가 이동할 계획서 내용이 주어집니다.(1 <= 이동횟수 <= 100)

- 문제풀이
1. 대표적인 시뮬레이션 문제
2. 요구사항대로 충실히 구현

```js
function ex1(n, direction) {
  // N 입력 받기, 초기값
  let x = 1, y = 1
  let nx = 1, ny = 1
  let plans = direction.split('')

  //이동방향
  let dx = [0, 0, -1, 1]
  let dy = [-1, 1, 0, 0]
  let move = ['L', 'R', 'U', 'D']

  // 이동 계획을 확인
  for (let i = 0; i < plans.length; i++) {
      for (let j = 0; j < move.length; j++) {
        //move에 맞는 다음 위치 값을 dx, dy 값을 찾아서 다음 위치값 설정
          if (plans[i] === move[j]) {
              nx = x + dx[j]
              ny = y + dy[j]
              // 다음 위치에 따라서 공간을 벗어나지 않는다면 실제로 이동하게함
              if (nx < 1 || ny < 1 or nx > n or ny > n) {
                  continue
              }
              x = nx
              y = ny
          }
      }
  }
  return `(${x},${y})`
}

console.log(ex1(5, 'R R R U D D'))
```


## 문제
알파벳 대문자와 숫자(0~9)로만 구성된 문자열이 입력으로 주어집니다. 이때 모든 알파벳을 오름차순으로 정렬하여 이어서 출력한 뒤에, 그 뒤에 모든 숫자를 더한 값을 이어서 출력합니다.

 - 입력조건

    첫째 줄에 하나의 문자열S가 주어집니다.(1 <= S의 길이 <= 10,000)

```js
  function ex2(input) {

  let arr = input.split("");
  let alph = [];
  let sum = 0;

  arr.forEach((s) => {
    if (s.match(/[A-Z]/gi)) alph.push(s);
    else sum += Number(s);
  });
  return alph.sort().join("") + sum;
}
//test
console.log(ex2("K1KA5CB7")); 
```
1. 초기값을 지정해준다.
2. 정규표현식을 이용해 입력 값에서 A-Z까지 찾아서 alph로 푸시하고, A-Z가 아니라 숫자일 경우 합쳐서 sum에 저장
3. 그 후 alph에 있는 값을 sort() 메소드를 이용해 오름차순으로 저장하고 join()메소드를 사용해 모든 요소를 하나의 문자열로 만들고 조건에 따라 마지막에 숫자만 합친 값을 출력