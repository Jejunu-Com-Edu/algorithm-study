# 최단경로 알고리즘 

최단 경로 문제란 가중 그래프에서 간선의 가중치의 합이 최소가 되는 경로를 찾는 문제이다.

 

1) 최단 경로 문제의 종류

단일 출발 (single-source) 최단 경로

어떤 하나의 정점에서 출발하여 나머지 모든 정점 까지의 최단 경로를 찾는 문제
단일 도착 (single-destination) 최단 경로

모든 정점에서 출발하여 어떤 하나의 정점까지의 최단 경로를 찾는 문제로 그래프 내의 간선들을 뒤집으면 단일 출발 최단거리 문제로 바뀔 수 있다.

단일 쌍(single-pair) 최단 경로

모든 정점 쌍들 사이의 최단 경로를 찾는 문제


2) 주요 알고리즘

- BFS (완전탐색 알고리즘)

가중치가 없거나 모든 가중치가 동일한 그래프에서 최단경로를 구하는 경우 가장 빠르다

- *다익스트라 알고리즘 (Dijkstra Algorithm)

음이 아닌 가중 그래프에서의 단일 쌍, 단일 출발, 단일 도착 최단 경로 문제

1. 출발 노드를 설정한다.
2. 최단 거리 테이블을 초기화한다.
3. 방문하지 않은 노드 중에서 최단 거리가 가장 짧은 노드를 선택한다.
4. 해당 노드를 거쳐 다른 노드로 가는 비용을 계산하여 최단 거리 테이블을 갱신한다.
5. 위 과정에서 3,4번을 반복한다.

- 벨만-포드 알고리즘 (Bellman-Ford-Moore Algorithm)

가중 그래프에서의 단일 쌍, 단일 출발, 단일 도착 최단 경로 문제

- *플로이드-워셜 알고리즘 (Floyd-Warshall Algorithm)

전체 쌍 최단 경로 문제
