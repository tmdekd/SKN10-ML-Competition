# **SKN10-ML-Competition**

### SK네트웍스 Family AI 캠프 10기 머신러닝 경진대회

<br/>

## **1. 프로젝트 개요**


  - **대회명**: SK네트웍스 Family AI 캠프 10기 머신러닝 경진대회
  - **과제**: Kaggle의 Titanic 데이터를 활용하여 승객의 생존 여부 예측 (Binary Classification)
  - **핵심 모델**: `LightGBM`
  - **최종 성적**: **6등**

<br/>
<p align="center"\>
<em>대회 개요 및 최종 순위</em>
<img width="1400" height="682" alt="스크린샷 2025-07-16 170353" src="https://github.com/user-attachments/assets/b1156d8b-6f5e-49ec-b64a-8c939e716983" />
<img width="1230" height="487" alt="스크린샷 2025-07-16 170418" src="https://github.com/user-attachments/assets/0af7d0fc-8e59-48be-a523-f6d774dddbe2" />
</p/>
<br/>

## **2. 주요 접근 방법**


모델의 예측 성능을 극대화하기 위해 데이터 분석부터 모델링까지 체계적으로 접근했습니다.

<br/>

### **데이터 분석 및 시각화 (EDA)**

각 변수(Pclass, Sex, Age, Fare 등)가 생존(Survived)에 미치는 영향을 분석하고, 시각화를 통해 데이터 분포와 변수 간의 관계를 파악하여 피처 엔지니어링의 기반을 마련했습니다.

<br/>

### **피처 엔지니어링 (Feature Engineering)**

  - **결측치 처리**
    > `Age`, `Cabin`, `Embarked` 등 주요 변수에 존재하는 결측치를 통계적 기법을 사용하여 합리적으로 처리했습니다.
  - **파생 변수 생성**
    >  - `SibSp` (형제자매/배우자 수)와 `Parch` (부모/자녀 수)를 통합하여 `FamilySize` (총 가족 수) 변수를 생성했습니다.
    >  - `Name` 칼럼에서 `Mr`, `Miss`, `Mrs` 등 사회적 신분을 나타내는 `Title`을 추출하여 새로운 범주형 변수로 활용했습니다.
  - **범주형 데이터 인코딩**
    > `Sex`, `Embarked`, `Title` 등 문자열 데이터를 원-핫 인코딩 또는 레이블 인코딩을 통해 모델이 학습 가능한 숫자형으로 변환했습니다.

<br/>

### **모델링 (Modeling)**

다양한 앙상블 모델 중, 대용량 데이터 처리 속도와 예측 성능이 뛰어난 \*\*`LightGBM`\*\*을 최종 모델로 채택했습니다. 교차 검증(Cross-validation)을 통해 모델의 일반화 성능을 확보하고 과적합을 방지했습니다.

<br/>

## **3. 디렉토리 구조**


```
SKN10-ML-Competition/
│
├── 📁 data/
│   └── (train.csv, test.csv, ...)
│
├── 📁 eda/
│   └── (EDA 관련 노트북)
│
├── 📁 model/
│   └── LightGBM_EDA2_submission_0213_7.ipynb
│
└── 📁 submission/
    └── (제출용 submission.csv 파일)

```

<br/>

## **4. 회고**


이번 경진대회는 데이터 정제와 피처 엔지니어링이 모델 성능에 얼마나 결정적인 영향을 미치는지 직접 경험하는 소중한 기회였습니다. 특히, 단순히 주어진 데이터를 사용하는 것을 넘어 `Title`이나 `FamilySize` 같은 새로운 파생 변수를 논리적으로 설계하는 과정이 예측 정확도를 높이는 핵심 요소임을 깨달았습니다.

`LightGBM` 모델의 강력함을 다시 한번 체감했으며, 교차 검증의 중요성과 하이퍼파라미터 튜닝의 필요성도 배울 수 있었습니다. 체계적인 디렉토리 구조를 통해 실험 과정을 관리하고 결과를 재현하는 습관의 중요성 또한 기를 수 있었던 의미 있는 프로젝트였습니다.
