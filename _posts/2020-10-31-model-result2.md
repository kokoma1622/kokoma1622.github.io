---
title: "[ML] Model Result2"
date: 2020-10-31 17:52:19 -0400
tags : [Machine Learning, Model Result]
categories: ML
---

앞의 글은 tanh을 activation으로 썼을 때까지만 정리.
relu에 최댓값 제한을 둔 relu6를 사용하니 결과가 조금(..) 더 좋음.

model 구조는 [8(3)], [32(3)], [64(3) pool 128(3)] 이고,
lr은 0.1^(3 ~ 6), activation은 relu6, stop patience = 10 이다.

10^(-3) ,, epoch 20, 75.72% ,, epoch 40, 75.41% ,, epoch 15, 75.80%

10^(-4) ,, epoch 20, 75.81% ,, epoch 22, 75.32% ,, epoch 25, 75.67%

10^(-5) ,, epoch 36, 75.64% ,, epoch 33, 75.80% ,, epoch 23, 75.89%

10^(-6) ,, epoch 55, 74.70% ,, epoch 27, 75.52% ,, epoch 16, 75.61%

[64(3) pool 128(3) 256(3)] 구조에 대해선 stop patience 값을 10과 20에 대해 학습을 진행하였다.


10^(-3) ,, epoch 14, 75.68% ,, epoch 31, 75.64%

10^(-4) ,, epoch 20, 75.81% ,, epoch 37, 75.67%

10^(-5) ,, epoch 11, 75.59% ,, epoch 100, 75.74%

10^(-6) ,, epoch 16, 75.57% ,, epoch 100, 75.71%

early stopping patience를 20으로 하니까, 작은 lr에 대해서는 100회 epoch로 early stopping이 되지 않는 것을 확인하였다.
결과들은 전반적으로 tanh에 비해 팽팽하게 판단하였다.
tanh은 90% ~ 80% 대로 예측되는 게임이 많았다면, 
relu6는 다양한 예상 승률 분포를 보였으며, 팽팽하게 느껴지는 데이터의 경우 50% 대의 예측도 자주 관찰되었다.
