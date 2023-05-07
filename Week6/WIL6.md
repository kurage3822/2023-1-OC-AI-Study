# 지도 학습

## 회귀 vs 분류

* 공통점

    회귀와 분류 모두 지도학습으로 독립변수와 종속변수가 있음

* 차이점

    종속변수가 회귀는 숫자로 연속형(Continuous), 분류는 이름으로 범주형(Categorical)임

## Classification Metrics

* TP

    True Positive : 실제 class가 Positive + 예측한 class도 Positive로 맞게 예측

* TN

    True Negative : 실제 class가 Negative + 예측한 class도 Negative로 맞게 예측

* FP

    False Positive : 실제 class는 Negative + 예측한 class가 Positive로 틀리게 예측

* FN

    False Negative : 실제 class는 Positive + 예측한 class가 Negative로 틀리게 예측

* precision

    정밀도 : 예측한 Positive 중 실제 Positive의 비율 : TP / (TP + FP)

* recall
    
    재현율 : 실제 Positive 중 예측한 Positive의 비율 : TP / (TP + FN)

* f1-score

    정밀도와 재현율의 조화평균 : (2 * 정밀도 * 재현율) / (정밀도 + 재현율)

* ROC-AUC

    모델의 성능을 나타내는 지표

## Over Sampling, Under Sampling

* Over Sampling

    부족한 데이터를 늘려 균형을 맞추는 방법

    * RandomOverSampler

        소수 클래스의 데이터를 반복해서 넣는 것

    * SMOTE
        Synthetic Minority Over-sampling Technique : ADASYN 방법처럼 데이터를 생성하지만 생성된 데이터를 무조건 소수 클래스라고 하지 않고 분류 모형에 따라 분류

    * ADASYN
        Adaptive Synthetic Sampling : 소수 클래스 데이터와 그 데이터에서 가장 가까운 k개의 소수 클래스 데이터 중 무작위로 선택된 데이터 사이의 직선상에 가상의 소수 클래스 데이터를 만드는 방법

* Under Sampling

    충분한 데이터를 줄여 균형을 맞추는 방법

## fit_sample vs fit_resample

* 공통점

    사용방법이 동일함

* 차이점

    0.4 버전 이상의 imblearn에서는 fit_sample를 더이상 지원하지 않음

    대신 fit_resample를 지원함

## Evaluation Metrics

* MAE

    평균 절대값 오차

* MSE

    평균 제곱 오차
 
* RMSE

    MSE에 루트를 씌운 값
    
* R^2
    결정계수 : 종속변인과 독립변인 사이에 상관관계가 높을수록 1에 가까워지며 값이 클수록 회귀모형의 유용성이 높다고 할 수 있음