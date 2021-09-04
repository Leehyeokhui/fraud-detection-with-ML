# fraud-detection-with-ML
ML 알고리즘과 불균형 데이터 처리를 이용한 fraud detection

머신러닝 스터디 진행 상황에 맞춰 전처리 및 모델 학습  
  
case 1.
 - 이상치 제거 안함
 - standard scaling
 - 9:1 비율로 train:test set split
 - model
   - logistic regression with penalty
   - decision tree
   - random forest
   - xg boost

case 2.
 - case 1에서 이상치 제거 후 진행
 - model
   - case 1
   - lightgbmboost
   - catboos

case 3.
 - case 2에서 SMOTE로 비대칭 데이터 oversampling
 - model은 case 2와 동일

case 4.
  - oversampling과 undersampling 모두 진행
  - 변수 선택 진행
  - model
    - case 3에서 xgboost 제외 후 adaboost 추가 후 진행
  - model 학습 후 가장 좋은 성능을 가진 model 2개로 stacking(xgboost 모델로 stacking 진행)

case 5.
 - 평균적으로 가장 좋은 성능을 보인 case 3의 모델들로 stacking 진행
 - decistion tree, random forest, xgboost, lbgmboost, catboost를 logistic model에 stacking 진행
 - logistic, decistion tree, random forest, lbgmboost, catboost를 xgboost model에 stacking 진행

여러가지 평가지표를 기준으로 top3 model을 선정했을 때  
case 3와 case 5의 성능이 좋은 모습을 보임

case 4는 case 3의 비해 대부분 model의 성능지표가 안좋아졌는데 undersampling 시 중요한 데이터가 drop 됐을 가능성이 있다.

