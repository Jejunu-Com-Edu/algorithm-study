# 최단경로 알고리즘이란?
---
+ 가장 짧은 경로를 찾는 알고리즘

<br>

# 최단경로 알고리즘
---
### 다양한 상황에서의 최단경로 찾기
	 상황 1) 한지점에서 다른 한지점
	 상황 2) 한 지점에서 다른 모든지점
	 상황 3) 모든 지점에서 다른 모든지점

+ 각 지점은 그래프에서 노드로 표현하고 지점간 연결된 도로는 간선으로 표현함
ex ) 마을과 마을을 있는 도로, 도시를 있는 통로 등등

<br>

## 1. 다익스트라 알고리즘
---

+ 출발 노드에서 다른 모든 노드로 가는 최단경로를 계산 (음의 간선 x 경우)
+ 매 상황에서 가장 비용이 적은 노드를 선택 -> 임의의 과정 반복 (일종의 그리디 알고리즘)

### 동작 과정
	1. 출발 노드를 설정
    
	2. 최단거리 테이블 초기화
    (자기자신을 제외한 모든 노드까지의 거리를 무한으로 설정, 자기 자신은 0으로 설정)
    
	3. 방문하지 않은 노드 중 최단거리가 가장 짧은 노드를 선택
    (이 과정을 통해 특정 노드까지의 최단거리를 확정짓는다, 모든 반복이 끝났을 때 전체노드까지의 최단거리가 나오게 됨)
    
	4. 해당노드를 거쳐 다른 노드로 가는 비용을 계산하여 테이블 갱신
    
	5. 과정 3, 4번을 반복
    
+ 최단거리 테이블은 각 노드에 대한 현재까지의 최단거리 정보를 가지고있음
+ 처리 과정에서 더 짧은 경로를 찾으면 최단거리 테이블을 그것으로 갱신

### 특징
+ 단계를 거쳐가며 한 번 처리된 노드의 최단거리는 고정되어 더 이상 바뀌지 않음
+ 그리디 알고리즘 - 매 상황에서 방문하지 않은 가장 비용이 적은 노드를 선택해 임의의 과정을 반복
+ 한 단계당 하나의 노드에 대한 최단거리를 확실히 찾는 것으로 이해할 수 있음
