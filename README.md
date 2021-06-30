# SWU-DS-Kaggle-A-DontOverFit

(한솔)
# SHAP
- 게임이론과 연관(여러 주제가 서로 영향을 미치는 상황에서 서로가 어떤 의사결정이나 행동을 하는지에 대해 이론화한 것)
## - Sharpley value : 
게임이론을 바탕으로 하나의 특성에 대한 중요도를 알기 위해 여러 특성들의 조합을 구성하고 해당 특성의 유무에 따른 평균적인 변화를 통해 얻어낸 값, 즉 모든 가능한 조합에 대해서 하나의 특성 기여도를 종합적으로 합한 값(한계 기여도의 평균)
<a href="https://ibb.co/Dws0L8c"><img src="https://i.ibb.co/h2h3CZQ/image.png" alt="image" border="0"></a>


- 단점) 
1.연산량이 매우 많아 비용이 많이 든다.
2. 입력값의 변화에 따른 예측값의 변화를 설명하기 어렵다.
3. 새로운 데이터에 대해 적용하기 힘들다.

- 장점) 비교/대조적 설명이 가능하다.

- 자료 출처 : https://datanetworkanalysis.github.io/2019/12/23/shap1


## SHAP
- SHAP는 게임이론을 다르는 최적의 Shapley Value를 기반으로 한다.
- SHAP의 목적 : 예측에 대한 각 특성의 기여도를 계산하여 관측치 x의 예측값을 설명한다.
- c연합을 shapley value 추정에서 얻을 수 있는 가중치에 다라 샘플링된 관측치에 가중치를 부여한다.

<a href="https://ibb.co/6rChhrk"><img src="https://i.ibb.co/34ZXX4n/1.png" alt="1" border="0"></a>

- 장점)
1. LIME과 Shapley value를 연결한다.
2. 트리 기반 모델을 빠르게 구현한다.
- 단점)
1. 속도가 느리다.

자료 출처 : https://datanetworkanalysis.github.io/2019/12/24/shap2


(혜은)
# ELI5
## 1. ELI5란?
시각화와 머신러닝 모델들을 API를 활용하여 디버깅 할 수 있도록 하는 파이썬 라이브러리 

*기타) 
1. ELI5(explain like I’m 5)_ 미국표현 중 하나인듯..?
- 약자 의미 : (주로 사용되지 않음) 
  -> 5살 아이가 이해할 수 있을 정도로 복잡한 주제를 간단하게 설명
- 주로 사용되는 의미 :
  -> 주제를 이해가 쉬운 형태로 쪼개서 읽는 사람들이 친숙한 언어로 바꿔설명하는 것
  
## 2. ELI5의 기능 : 
1) 머신러닝 framework 내부에 설치되어있어, 블랙박스 모델을 설명하는 방법을 제공한다. 
2) 머신러닝 모델들의 디버깅을 가능하게 한다
3) 머신러닝 모델들의 예측결과를 설명한다. 

## 3. ELI5가 가능한 머신러닝 모델 및 패키지 : 
1) scikit-learn
2) Keras
3) XGBoost
4) LightGBM
5) CatBoost
6) lightning
7) sklearn-crfsuite

## 4. 활용방법 
1) 분류 및 회귀모델
- eli5.show_weights() : 모델 파라미터 확인하고, 모델 작동 방법을 확인
<img width="113" alt="1" src="https://user-images.githubusercontent.com/68270643/123999515-94c06980-da0d-11eb-94cd-2e877480c3df.PNG">
- eli5.show_prediction() : 모델의 개별 예측결과를 확인하고, 그 결과가 나오게 된 이유 확인
<img width="325" alt="2" src="https://user-images.githubusercontent.com/68270643/123999564-9ee26800-da0d-11eb-859d-06936b996dfd.PNG">

2) titanic 예시 
(링크 : https://eli5.readthedocs.io/en/latest/tutorials/xgboost-titanic.html)
- 일반 코드와 ELI5 차이점 
1) 가중치
<img width="504" alt="weight" src="https://user-images.githubusercontent.com/68270643/123999893-f4b71000-da0d-11eb-82ca-ad0a709b0b9c.PNG">
### ElI5

<img width="429" alt="weight2" src="https://user-images.githubusercontent.com/68270643/123999965-0e585780-da0e-11eb-9dfe-3785c478f772.PNG">
3) 예측
### ElI5

<img width="264" alt="prediction" src="https://user-images.githubusercontent.com/68270643/123999897-f680d380-da0d-11eb-836c-ce40888366f1.PNG">

4) Null값
<img width="264" alt="null" src="https://user-images.githubusercontent.com/68270643/123999901-f7b20080-da0d-11eb-9ac0-931ebeba7da9.PNG">


(하영) 
<h4> 1. K-fold 교차검증을 하는 이유? </h4>
<h5> &nbsp; 기본적으로는 셔플없이 데이터 세트를 K번 연속 폴드로 나눈다. 그런다음 각 폴드는 검증세트로 한 번 사용되고 나머지는 매번 트레이닝 세트의 역할을 한다. 데이터 수가 적으면 데이터의 일부인 유효성 검사의 수 또한 적기 때문에 유효성 검사의 신뢰성이 좋지 않다. 그러나 유효성 검사 데이터의 수가 증가하면 훈련 데이터의 수가 적어지기 때문에 정상적인 학습 프로세스가 불가능하다.  따라서 이 딜레마를 해결하기 위한 것이 바로 K-fold 교차검증이다. </h5>
<h4> 2. K-fold 교차검증에서의 학습과 검증 </h4>
<h5> &nbsp; 전체 데이터를 K부분 집합으로 나눈다. 예를 들어 5세트를 만들면 4세트가 학습 데이터가 되고 5번째 세트는 유효성 검사를 위한 것이 되는 것이다. 이어 검증은 4번째 세트로 하고 나머지는 훈련 데이터로 사용한다. 이런식으로 세번째, 두번째, 첫번째도 해나가면 총 5개의 모델 또는 k 모델이 K번 교차 검증하게 되는 것이다. </h5>
<a href="https://ibb.co/gM8RCcw"><img src="https://i.ibb.co/PZy68V4/Kfold.jpg" alt="Kfold" border="0"></a>
<h4> 3. StratifiedKFold </h4>
<h5> &nbsp; 계층화된 폴드를 반환하는 K-폴드의 변형이다. 각 세트에는 각 세트의 샘플이 전체 세트와 거의 같은 비율로 포함되어 있고 데이터가 편향되면 K-폴드 교차 검증이 제대로 수행되지 않을 수 있다.
그래서 트레인 세트와 유효성 검사 세트를 여기저기서 수집한다.
</h5>
<a href="https://ibb.co/vqFVWxz"><img src="https://i.ibb.co/tKGQ6MC/KFold2.jpg" alt="KFold2" border="0"></a>
<h4> 4. K-fold와 StratifiedKFold의 차이 </h4>
<h5> &nbsp; 일반적으로 K-Fold는 회귀에 사용되며 StratifiedKFold는 분류에 사용된다.
</h5>
<h4> 5. RepeatedStratifiedKFold </h4>
<h5> &nbsp; RepeatedStratifiedKFold는 StratifiedKFold와 비슷하지만 그 안에서 여러번 반복되는 것이 다르다.
RepeatedStratifiedKFold는 각 반복마다 또 랜덤으로 n번 반복한다.
즉, 교차 검증 내부에 교차 검증이 있다.
</h5>
<a href="https://ibb.co/m0Q3Hrf"><img src="https://i.ibb.co/3vtn05g/KFold3.jpg" alt="KFold3" border="0"></a>
