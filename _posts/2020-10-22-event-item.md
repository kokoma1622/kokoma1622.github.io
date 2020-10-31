---
title: "[DB] Event Item"
date: 2020-10-22 01:07:41 -0400
categories: DB
---

Table Event Item

gameid/tstamp

userid : 아이템 관련 행동을 한 유저.

action : 아이템 관련 행동. PURCHASE/SELL/GANGPLANK/HERALD/MURAMANA/SERAPH/SUP_QUEST/WATCH_KIT/WATCH_USE/YOURCUT.
item destroy와 관련해서는, 소모성 아이템 사용과 상위템으로 업그레이드 시 사라지는 하위템은 기록하지 않음.
이를 제외하고, 차례로 갱플랭크 궁극기 업그레이드/전령 사용/무라마나 완성/대천사 완성/서폿템 완료/초시계키트 완성/초시계 사용/파이크 수당 사용.

itemid : 아이템 관련 행동이 있는 아이템의 id.

keywords : sql, structure
