---
title: "[ML] Hyperparameter selection"
date: 2020-10-23 00:18:12 -0400
categories: machinelearning, CNN, hyperparameter
---

원하는 image 데이터셋을 만드는 것까지 성공했으니, 모델을 설계하고 관련 변수들을 세팅할 차례이다.
image는 28x28x12로 크기는 작고 channel은 많은 형태이다. 

막대그래프의 너비와 간격이 각각 2이기 때문에,
kernel size를 3으로 하면 인접한 두 막대의 비교가 힘들 것으로 예상되어 5로 설정하였다.
3으로 해도 두 번째 layer에서 확인할 수 있기도 하니, 3도 나중에 해보았다.
커널 개수와 레이어 개수, 풀링의 위치 등을 여러 가지로 조합해서 학습하였다.

또한 optimizer는 adam과 rmsprop을 사용하였는데,
1 epoch에만 대략 7k step이 있다보니 learning rate decay가 지속적으로 일어나는 문제가 있었다.
adam은 알고리즘 상 step decay가 계속 일어날 수밖에 없어
