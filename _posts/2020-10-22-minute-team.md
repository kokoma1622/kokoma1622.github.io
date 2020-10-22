---
title: "[DB Table] Minute Team"
date: 2020-10-22 00:54:10 -0400
categories: sql, structure
---

Table Minute Team

minute personal table을 개인->팀으로 바꾼 느낌

gameid/minute/golds/kills/towers

dragons : 2d array의 경우 arr[0]와 arr[1]의 길이가 같아야한다. (postgresql의 규칙)
이를 위해 팀이 먹은 용의 수가 다를 경우, _ 를 추가하여 길이를 맞춰주었다.
