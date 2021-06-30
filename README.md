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
- (이미지 첨부)
- eli5.show_prediction() : 모델의 개별 예측결과를 확인하고, 그 결과가 나오게 된 이유 확인
(이미지 첨부)

2) titanic 예시 
(링크 : https://eli5.readthedocs.io/en/latest/tutorials/xgboost-titanic.html)
- 일반 코드와 ELI5 차이점 
1) 가중치
(이미지 첨부)
3) 예측
(이미지 첨부)




(하영) \\(^-^)/
