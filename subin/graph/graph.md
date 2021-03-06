# 그래프
: 노드와 노드 사이에 연결된 간선의 정보를 가지고 있는 자료구조

'서로 다른 개체(혹은 객체)가 연결되어 있다'

'여러 개의 도시가 연결되어 있다'

➔ 그래프 문제!

### 그래프 구현 방법
- 인접 행렬(Adjacency Matrix) : 2차원 배열을 사용하는 방식(플로이드 워셜 알고리즘)
- 인접 리스트(Adjacency List) : 리스트를 사용하는 방식 (다익스트라 최단 경로 알고리즘)

! 어떤 문제를 만나든 메모리와 시간을 염두 !

<br>

최단 경로 문제 
- 노드의 개수가 적은 경우 : 플로이드 워셜 알고리즘
- 노드의 개수가 많은 경우 : 다익스트라 알고리즘

### 서로소 집합
: 서로소 부분 집합들로 나누어진 원소들의 데이터를 처리하기 위한 자료구조

트리 활용
1. union(합집합) 연산을 확인하여, 서로 연결된 두 노드 A, B를 확인한다.
- A와 B의 루트노드 A', B'를 각각 찾는다.
- A'를 B'의 부모 노드로 설정한다(B'가 A'를 가리키도록 한다).
2. 모든 union(합집합) 연산을 처리할 때까지 1번 과정을 반복한다.


### 신장 트리
: 하나의 그래프가 있을 때 모든 노드를 포함하면서 사이클이 존재하지 않는 부분 그래프


크루스칼 알고리즘
1. 간선 데이터를 비용에 따라 오름차순으로 정렬한다.
2. 간선을 하나씩 확인하며 현재의 간선이 사이클을 발생시키는지 확인한다.
- 사이클이 발생하지 않는 경우 최소 신장 트리에 포함시킨다.
- 사이클이 발생하는 경우 최소 신장 트리에 포함시키지 않는다.
3. 모든 간선에 대하여 2번의 과정을 반복한다.


### 위상 정렬 
: 방향 그래프의 모든 노드를 '방향성에 거스르지 않도록 순서대로 나열하는 것'

1. 진입차수가 0인 노드를 큐에 넣는다.
2. 큐가 빌 때까지 다음의 과정을 반복한다.
- 큐에서 원소를 꺼내 해당 노드에서 출발하는 간선을 그래프에서 제거한다.
- 새롭게 진입차수가 0이 된 노드를 큐에 넣는다.

