---
title: "[ML] Model Result"
date: 2020-10-28 22:58:19 -0400
tags : [Machine Learning, Model Result]
categories: ML
---

image size를 14x14x12로 정한 후의 결과만 기록하였다.
28x28x12로 설계한 model들도 있으나, 이 글에선 제외하였다.
거의 항상 75퍼센트의 정확도를 보였다.
model structure, learning rate, dropout, activation, optimizer, early stopping, training epoch에 변화를 줬다.

숫자들은 conv2d layey의 kernel 개수, 크기를 의미한다.
아래 데이터들은 lr = 0.00001, activation=relu, AdamP optimizer 사용하여 러닝한 결과이다.

[8(3)] : 75.85%

[8(3)] with dropout : 75.89%

[32(3), pool, 64(3)] : 74.54% , overfitting 추측

[32(3), pool, 64(3)] with dropout : 75.87%

[64(3), pool, 128(3), pool, 256(3)] with dropout : 75.84%

여기서 사용한 모델들을 저장하고, 미리 만들어놓은 테스트 데이터셋이 아니라 내가 새로 만든 내 솔랭 결과 데이터를 승패 예측에 넣어보았다.
그런데 AdamP optimizer는 keras 내장이 아니라서 model을 load할 때 문제가 생겼다.
아마 방법이 있긴 하겠지만, 찾기 힘들어서 Adam optimizer를 사용하였다.
기본 adam optimizer를 사용하여 lr = 0.001으로, 정확도는 75.95%로 확인되었다.
이 model로 내 솔랭 결과 데이터로 승부 예측을 해보니, softmax 결과가 0과 1로만 나왔다.
이미 승패가 결정된 상황이라 그런가 생각하여 롤드컵 4강 경기 중의 상황을 입력으로 넣어보았으나, 역시 0과 1로만 출력되었다.

둘(블루팀승리/레드팀승리) 사이의 값 차이가 어디에서 크게 벌어졌기에, softmax가 0과 1로만 나온다고 추측하였다.
모델을 새로 만들 때 lr을 낮추고, activation을 tanh로 바꿔보았다.
그 결과 relu activation이 큰 값을 걸러주지 못하기에 결과가 단정적으로 나오게 되었다고 확인할 수 있었다.
아무래도 lr을 낮추면 training epoch가 더 많이 필요할 것이고, 그러다보면 overfitting이 발생할 수도 있다고 생각하여,
early stopping을 도입하여 가장 단순한 모델인 8(3)을 lr을 0.1^3에서 0.1^6까지 바꿔가며 학습하였다.
아래 내용은 early stopping 기준을 5회/10회로 잡았을 때의 학습 결과이다. 

앞에서부터 lr, 멈춘 epoch, accuracy [stop patience = 5], 멈춘 epoch, accuracy [stop patience = 10]

10^(-3), epoch 15, 75.62%,, epoch 23, 75.45%

10^(-4), epoch 11, 75.24%,, epoch 32, 75.62%

10^(-5), epoch 11, 75.38%,, epoch 22, 75.66%

10^(-6), epoch 39, 75.16%,, epoch 33, 75.16%

0과 1만 나오던 softmax 결과가 0.3 0.4 등 다양하게 나오기 시작했다.
게임 2분의 데이터 결과는 챔프만 보고 승패 예측을 하는 것이기 때문에 모델에 따라 승패 예측이 많이 달랐다.
내 랭크 결과는 승패 예측 결과가 90% 대로 나왔다.
맞라이너와 팀을 바꿔서 결과를 비교했을 때 확률이 변하는데, 이를 통해 팀에 얼마나 기여했는지 간접적으로 확인이 가능했다.
예를 들어 탑끼리 바꿨을 때 예상 승률 80%->90%로 바뀌면 탑이 구멍이라는 뜻.
그리고 lr = 10^(-6)의 경우 학습이 덜 되고 멈추는듯하다.
아마 lr이 지나치게 작다보니 stop patience = 10이 충분치 않았던 느낌.
