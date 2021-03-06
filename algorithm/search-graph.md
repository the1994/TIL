# 그래프 탐색 

## 너비 우선 탐색 
- 시작점에서 목표인 정점을 탐색할 때 시작점에 가까운 정점부터 탐색하는 방식 
- 후보 선택 기준은 후보중 가장 먼저 후보에 추가 된 것
- 후보 정점은 '선입선출' 구조로 '큐' 데이터 구조를 이용할 수 있다. 

## 깊이 우선 탐색 
- 정점을 탐색할 때 하나의 길을 끝까지 따라가다가 더 이상 진행할 수 없는 곳에 다다르면 다음 후보가 되는 길을 따라감 
- 후보 선택 기준은 후보 중 가장 최근에(늦게) 추가된 것 
- 후보 정점은 '후입선출' 구조로 '스택' 데이터 구조를 이용할 수 있다. 

## 벨먼-포드 알고리즘
- 그래프의 최단 경로 문제를 해결하기 위한 알고리즘 
- 최단 경로 문제에서는 간선에 가중치가 부여된 '가중 그래프'가 주어진다.
- 시작점과 종점까지의 경로 중에 가중치의 합이 가장 작은 것을 구하기 

