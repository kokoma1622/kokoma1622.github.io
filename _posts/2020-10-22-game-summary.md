---
title: "[DB] Game Summary"
date: 2020-10-21 21:44:21 -0400
categories: DB
---

Table Game Summary

gameid : 해당 게임에 부여된 고유한 id. 게임이 플레이 된 시점에 관련이 있다. 나중에 플레이된 게임일수록 gameid가 크긴 한데, 정확한 시간 기준은 모름.

season : 해당 게임의 시즌. 올해는 시즌 10.

version : 해당 게임의 패치 버전. 1 ~ 25로 예정되어있음. DB에 담긴 게임은 21버전까지.

win : 해당 게임의 이긴 팀. BLUE팀과 RED팀 중 택일. 

tier  : 해당 게임 유저들의 평균 티어. 다2까지는 1점씩 주고, 다1 마스터 그마 챌린저는 2점 간격을 부여하여, 1 ~ 30점으로 점수를 매긴 후 10명을 평균내어 다시 티어로 변환.

creation : 해당 게임이 생성된 시간. riot-api에 따르면 밴픽이 끝난 후 게임 로딩이 시작된 시간이라 함. timestamp * 1000 데이터로 KST 변환을 통해 한국 시각으로 변환 가능.

duration : 해당 게임의 플레이 타임을 초 단위로 표현.

keywords : sql, structure
