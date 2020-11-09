---
title: "Linear Regression"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: machine_learning
meta_keywords: 머신러닝, linear regression
date: 2020-05-09 21:00:00 -0400
---

1. Simple models for Prediction
   > 상품 판매량을 예측하는 가장 간단한 방법은 무엇일까요?

- Model 1 - 평균 판매량:
  머신러닝에 대한 지식이 없어도, 만일 어떤 item의 판매량을 예측해야 한다면 당신은 최근 몇일간/몇달간/몇주간 해당 item의 평균 판매량으로 계산할 것이다<br>
  모델이 얼마나 정확한가 측정하는 가장 흔한 방법은 MSE(Mean Squared Error)이다.<br>

  - MSE
    ![mse](./assets/images/post/mse.png)
    제곱된 에러의 합을 데이터 수만큼 나눠줌으로써 데이터 수에 따른 bias를 제거한다.

- Model 2 - 지역에 따른 평균 판매량:
  각각의 location type의 평균 매출량을 계산하고 그에 맞게 예측을 한다고 해보자. 매출 판매량의 예측에 대한 MSE는, Model 1에서의 결과값보다 작게 나오게 된다. 그렇다면 우리는 '지역'이라는 특성이 error 값을 줄여줬다는 것을 알 수 있게 된다.<br>
  그렇다면 판매량이 여러 개의 변수들에 의해 영향을 받는다면, 우리는 이 정보들을 이용해서 어떻게 판매량을 예측할 수 있을까? 이런 문제를 해결하기 위해 Linear regression이 등장한다.

2. Linear Regression

3. Ridge Regression
   λ는 기존의 잔차 제곱합과 추가적 제약 조건의 비중을 조절하기 위한 하이퍼 모수(hyper parameter)이다. λ가 크면 정규화 정도가 커지고 가중치의 값들이 작아진다. λ가 작아지면 정규화 정도가 작아지며 λ가 0이 되면 일반적인 선형 회귀모형이 된다.

Ridge 모형은 가중치 계수를 한꺼번에 축소시키는데 반해 Lasso 모형은 일부 가중치 계수가 먼저 0으로 수렴하는 특성이 있다.

- 출처
  [https://brunch.co.kr/@itschloe1/9]
