---
title: "[DB] Personal Summary"
date: 2020-10-21 21:44:21 -0400
tags: [sql, structure]
categories: DB
---

Table Personal Summary

gameid : 모든 테이블에 존재. 게임을 구분하는 key 역할.

userid : 해당 유저에게 배정된 1 ~ 10 까지의 id. 블루 팀 유저에 1 ~ 5, 레드팀 유저에 6 ~ 10이 배정된다.

team : 해당 유저의 팀. BLUE/RED

win : 해당 유저가 승리했는지 패배했는지. VICTORY/DEFEAT

nickname : 해당 유저의 소환사 명

role : 해당 유저의 해당 게임에서의 포지션. riot api서 제공하는 role 정보는 부정확하여,
아이템(서폿)과 스펠(강타), 라인전 단계에서의 위치 빈도로 포지션을 배정. TOP/JUNGLE/MID/BOTTOM/SUPPORT/UNSPECIFIED

champion : 해당 유저의 챔피언 id. 1 ~ 999 까지 riot이 미리 배정해놓은 숫자.

level : 해당 유저의 게임이 끝날 때 레벨.

kills : 총 킬

deaths : 총 데스

assists : 총 어시스트

spells : 소환사 주문 id list.

gold : 총 골드

items : 가지고 있던 item id list. list의 마지막은 장신구

skilltree : 찍은 스킬을 순서대로 qwer로 이루어진 string 형태로 표현. 카직스나 카이사 같이 스킬 진화하는 경우는 무시하고 레벨업을 통한 스킬포인트만 기록.
