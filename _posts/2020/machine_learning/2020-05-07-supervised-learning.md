---
title: "Supervised Learning vs Unsupervised Learning"
excerpt: 'Machine Learning'
comments: true

categories:
    - Machine Learning
tags:
    - [Machine Learning, 머신러닝]
toc: true
toc_sticky: true
date: 2020-05-07 04:58:00 -0400
---

1. Supervised Learning (지도 학습)<br>
   지도 학습은 컴퓨터에게 정답(label)이 무엇인지 알려주면서 컴퓨터를 학습하는 방법입니다.<br>
   예를 들어 3x5=15, 6x4=24 등을 학습시킨 후 9x3=?? 등의 주어진 문제를 해결하는 학습 방법입니다.<br>
   여기서 3x5는 data이고 정답인 15는 label이라고 표현합니다. 그렇기 때문에 지도 학습에는 정확한 input과 output이 존재하며, 이러한 지도 학습에는 분류(Classification)와 회기(Regression)로 나누어집니다.

- 분류 (Classification)
  먼저 분류(Classification)는 주어진 데이터를 정해진 카테고리에 따라 분류하는 문제를 말합니다.<br>
  최근에 많이 사용되는 이미지 분류도 Classification 문제 중에 하나입니다.<br>
  darknet YOLO의 network architecture는 GoodLeNet for image classification를 이용하여 이미지를 분류하고 있습니다.<br>

  예를 들어 스팸메일을 예측한다고 가정했을 경우 해당 메일이 스팸인가? 스팸메일 / 일반 메일로 라벨링 될 수 있을 것입니다. 이처럼 예, 아니오로 구분될 수 있는 분류를 Binary Classification이라고 부릅니다.

  하지만 문제는 예, 아니오로 구분되지 않을 수 있습니다. 예를 들어 이 동물이 무엇일까?라고 했을 때 강아지, 고양이, 나무늘보 등으로 예측하는 상황이 있습니다. 이러한 분류를 Multi-label Classification이라고 합니다.

- 회귀 (Regression)
  Regression은 어떤 데이터들의 특징(Feature)을 기준으로 연속된 값을 예측하는 문제입니다. (연속된 값이란 그래프를 생각하면 됩니다.)<br>
  주로 어떤 패턴이나 트렌드, 경향을 예측할 때 사용되며, 일반적으로 집의 크기에 대해 매매 가격을 예로 듭니다.<br>
  Q. 강남에 30평대 아파트면 집값이 어느 정도야?<br>
  A. 강남에 30평대 아파트면 OO억정도 입니다.

  지도 학습의 가장 큰 문제 또는 장벽은 정답 집합을 확보하는 것입니다. 따라서 비지도 학습을 통해 지도 학습의 단점을 보완하기 위해 비지도 학습에 대한 중요성과 관심이 높아지고 있습니다.

2. Unsupervised Learning (비지도 학습)<br>
   지도 학습과는 달리 정답을 알려주지 않고 비슷한 데이터를 군집화 하여 미래를 예측하는 학습 방법입니다.<br>
   라벨링이 되어있지 않은 데이터로부터 패턴이나 형태를 찾아 야하기 때문에 어렵습니다.<br>
   실제로 지도 학습에서 적절한 특징(Feature)을 찾아내기 위한 전처리 방법으로 비지도 학습을 사용하기도 합니다.

   비지도 학습은 대표적으로 클러스터링(Clustering)이 있습니다. 일반적으로 데이터는 Label이나 Category가 무엇인지 알 수 없는 경우가 많기 때문에 이러한 방법이 중요하다고 볼 수 있습니다. 이외에도 차원 축소 (Dimentionality Reduction), Hidden Markov Model이 있습니다.

   예를 들어 강아지, 고양이, 기린, 원숭이 사진을 비지도 학습으로 분류한다고 가정해보겠습니다.<br>
   각각의 동물들이 어떤 동물인지 정답을 알려주지 않았기 때문에 이 동물을 '무엇' 이라고는 정의할 수는 없지만 동물의 특징(Feature) 별로 분류를 하게 됩니다.

   다리가 4개인 강아지, 고양이, 기린은 한 분류가 될 수 있고<br>
   또는 목이 긴 기린이 한 분류,<br>
   다리가 2개인 원숭이가 한 분류로 나뉘게 될 것입니다.

   따라서 비지도 학습은 예측 등이 아닌 데이터가 어떻게 구성되어있는지 밝히는데 주로 사용하고, 일종의 그룹핑 알고리즘으로 볼 수 있습니다.

- 지도 학습, 비지도 학습의 대표 알고리즘

<table style="border-collapse: collapse; width: 100%; height: 280px;" border="1" data-ke-style="style4">
    <tbody>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 160px;" rowspan="8">&nbsp;지도학습(Supervised <span id="DragSchLayerPos" style="position: absolute; width: 0px; height: 0px; font-size: 0px;"></span>Learning),</td>
            <td style="width: 33.3333%; height: 80px;" rowspan="4">&nbsp;Classification</td>
            <td style="width: 33.3333%; height: 20px;">&nbsp;kNN</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;Naive Bayes</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;Support Vector</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;Machine Decision</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 80px;" rowspan="4">&nbsp;Regression</td>
            <td style="width: 33.3333%; height: 20px;">&nbsp;Linear Regression</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;Locally Weighted Linear</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;Ridge</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;Lasso</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 120px;" rowspan="6">&nbsp;비지도학습(Unsupervised Learning),<br><br></td>
            <td style="width: 33.3333%; height: 120px;" rowspan="6">&nbsp;</td>
            <td style="width: 33.3333%; height: 20px;">&nbsp;Clustering</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;K Means</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;Density Estimation</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;Exception Maximization</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;Pazen Window</td>
        </tr>
        <tr style="height: 20px;">
            <td style="width: 33.3333%; height: 20px;">&nbsp;DBSCAN</td>
        </tr>
    </tbody>
</table>

- 출처
  [https://wendys.tistory.com/169]
