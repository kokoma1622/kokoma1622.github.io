---
title: "[DB Table] Team Summary"
date: 2020-10-21 23:47:01 -0400
categories: sql, structure
---

Table Team Summary

gameid / team

win : 해당 팀이 승리했는지. VICTORY/DEFEAT

champions : 해당 팀의 챔피언 id들 size of 5

bans : 해당 팀이 밴한 챔피언 id들 size of 5. 밴하지 않은 경우 -1

firsts : 해당 팀의 퍼스트 ** 여부 size of 6. 킬/타워/억제기/용/바론/전령

totals : 해당 팀의 전체 ** 여부 size of 6. 킬/타워/억제기/용/바론/전령

dragons : 해당 팀이 먹은 용, size of 전체 용. 먹은 용의 종류를 list의 원소로.
