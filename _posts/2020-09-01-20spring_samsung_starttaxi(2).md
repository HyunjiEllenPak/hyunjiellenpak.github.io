---
title: 삼성전자 20상반기 코테 풀이(2) - 스타트 택시
categories:
    - algorithm
date: 2020-09-19 00:47:00 +0900
tags: [Algorithm, Samsung]        
comments: true
toc: False
---

문제 설명
==================================================================================================
삼성전자 올 상반기 공채 SW 테스트 문제였던 "스타트 택시" 문제를 풀어보려 한다.

이 문제의 주요 내용은 다음과 같다.

1. N x N 크기의 격자에서 각 칸은 비어있거나 벽이 놓여있다. 택시가 빈칸에 있을 때 상하좌우로 인접한 빈칸 중 하나로  이동할 수 있다. 이때 최단경로로만 이동한다.
 - 최단 경로인 승객이 여러명인 경우, 행이 작은 승객을, 여러명인 경우 열이 작은 승객을 태움 
2. M명의 승객은 빈칸에 서있으며 다른 빈칸으로 이동하려 한다.
3. 한번에 한 승객만 탑승하고 출발지에서 택시타서 도착지에서 택시에서 내린다.
4. 택시에 태울 승객을 선정할때 최단 거리에 있는 승객, 행번호 작은 승객, 열번호 작은 승객의 우선순위를 두고 승객을 선정한다.
5. 택시 한칸 이동시마다 연료 1 소모, 한 승객 이동완료하면 승객이동하면서 소모한 연료 2배가 충전되나 이동 도중 연료 소모시 택시 운행 중단한다. 
6. 모든 승객을 성공적으로 이동시킬 수 있는 경우 최종 남은 연료를, 이동시킬 수 없는 경우 -1을 리턴하라
 
풀이 방법
=======================================================================================================

1. 택시 태울 승객 선정
 - BFS로 택시로부터 가장 가까운 승객들 구하고
 - 여러명인 경우 행,열번호로 sort 해서 한명 선택.
2. 태운승객의 출발지 to 목적지의 최단거리 계산
 - BFS로 출발지에서 목적지까지 최단 거리 계산
3. 1,2 진행하면서 연료 모두 소진되는 경우 운행 중단. 

- 주의사항: 삼성 코테 문제중에서 비교적 난이도가 높은 편, 문제에 여러가지 조건들이 많아서, 잊지말고 모두 고려해줘야함. 
- 사용 언어: C++
- 알고리즘: Queue를 이용한 BFS 알고리즘 사용.
<script src="https://gist.github.com/HyunjiEllenPak/bcd1bf899737043a2df96deb75018073.js"></script>