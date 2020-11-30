---
title: "Parametric Method vs Nonparametric Method"
layout: single
author_profile: true
read_time: true
comments: true
share: true
related: true
categories: machine_learning
meta_keywords: 머신러닝, parametric method
date: 2020-05-07 05:10:00 -0400
---

1. Parametric Method
   parametric method는 2 step으로 이루어져있습니다.<br>

1)  f의 형태를 가정한다.<br>
    예를 들어, f를 가정하는 가장 간단한 방법은 선형으로 가정하는 것입니다.

                      f(X) = β0 + β1*X1+β2*X2+......βp*Xp

2)  모수(β)를 추정합니다. (보통 least square estimation 최소제곱추정법을 사용합니다. 쉽게 말해 실제 y와 예측한 y의 차이를 최소화하는 방법입니다.)

위 두가지 단계를 거치면 우리는 추정한 f를 얻을 수 있습니다.
