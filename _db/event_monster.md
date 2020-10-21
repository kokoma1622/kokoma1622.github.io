---
title: "EventMonster"
date: 2020-10-22 01:01:01 -0400
categories: sql, structure
---

Table Event Monster

gameid/tstamp

userid : 용/바론/전령을 처치한 유저. 전령이 퇴근해도 -1처리라 지움. 샤코 분신이 처치하면 -1로 처리되는 문제가 있었음.
사일과 샤코가 다른 팀으로 함께 있으면 사일 팀에서도 발생하던 문제. 팀 전체 몬스터 처리 수를 비교하며 팀과 유저 지정

team : 처치한 팀

monster : 바론 BARON 전령 HERALD 용 DRAGON_(종류)
