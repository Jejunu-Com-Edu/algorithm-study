# BFS
---
+ 다차원 배열에서 각 칸을 방문할 때 너비를 우선으로 방문하는 알고리즘
<br>

## 예시
---
1. 시작하는 칸을 큐에 넣고 방문했다는 표시를 남김
2. 큐에서 원소를 꺼내어 그 칸에 상하좌우로 인접한 칸에 대해 3번을 진행
3. 해당 칸을 이전에 방문했다면 아무 것도 하지 않고, 처음으로 방문했다면 방문했다는 표시를 남기고 해당 칸을 큐에 삽입
4. 큐가 빌 때 까지 2번을 반복
<br>
모든 칸이 큐에 1번씩 들어가므로 시간복잡도는 칸이 N개일 때 O(N)
<br>

## 연습 문제
---
1926 - 그림
2178 - 미로 탐색
7576 - 토마토
4179 - 불!
1697 - 숨바꼭질
<br>

---
[출처](https://blog.encrypted.gg/941?category=773649)