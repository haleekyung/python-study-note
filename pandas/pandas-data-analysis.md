## 판다스의 데이터 분석
판다스 데이터 분석 전 아래의 기본 세팅은 반드시 시행할 것

``` python
# 판다스 없으면 설치하기
pip install pandas

# pandas, re, os 모듈
import pandas as pd
import re, os

# 경로 모를 때 확인
os.getcwd()

# 경로 설정
os.chdir(r'/경로')

# 판다스로 csv를 불러올 때 해당 함수 사용
df = pd.read_csv('파일명.csv')
```

### 1. 판다스로 가져온 csv파일에 대한 기본분석

**1) 기본 코드 : df.함수명()**

- **특정 행에 대한 값 구할 때 : df.행이름.함수명()**

**2) 각 함수 별 기능**

- `df.describe()` : 기초통계량
    - count / mean / std / min / 25% / 50% / 75% / max
- `df.value_count()` : 빈도분석 (몇 명의 사람들이 응답했는가)
- `df.mean()` : 평균값
- `df.median()` : 중간값
- `df.sum()` : 합
- `df.std()` : 표준편차
- `df.var()` : variance
- `df.groupby.(df.행이름).함수명()` : 그룹별로 나누기
    - `df.groupby.(df.sex).mean()` : 성별을 기준으로 평균 내기

## 2. 싸이파이(scipy)를 이용한 데이터 분석

### **1) 싸이파이(scipy) 설치**

```python
# 싸이파이 설치하기 (이거 혼자만 두고 설치해야 됨)
pip install scipy
```

```python
# 싸이파이 내부 통계모듈만 불러오기
from scipy import stats
```

```python
# 나머지 모듈 불러오기
import pandas as pd
import os, re
```

### 2) 결과를 집단별로 나누어 다른 객체로 저장

```python
객체명 = df.행이름[df.행이름 == '행 내부 값']

# 예시
# 결과를 바탕으로 남성의 수입과 여성의 수입으로 나누겠다
male = df2.income[df2.sex == 'm']
female = df2.income[df2.sex == 'f']
```

## 3) T검정 (T-test)

- `stats.ttest_ind(변수명1, 변수명2)` : T검정하기
    - 결과값으로 t-test값의 결과([0])와 p-value값([1])을 볼 수 있다.
    - t-test 값은 [0]번째 리스트로 저장될 수 있음
    - p-value 값은 [1]번째 리스트로 저장될 수 있음


- t-test의 결과값은 변수로 저장할 수 있다.
    - `ttest_result(변수명) = stats.ttest_ind(변수명1, 변수명2)`
    - `ttest_result[0]` : t-test 값
    - `ttest_result[1]` : p-value 값


- t-test의 값이 유의한지 알아볼 수 있는 조건문을 통해 유의여부를 한눈에 볼 수 있다.

    ```python
    if ttest_result[1] > .05:
        print('p-value는 %f로 95% 수준에서 유의하지 않음' % ttest_result[1])
    else:
        print('p-value는 %f로 95% 수준에서 유의함' % ttest_result[1])
    ```

### 4) 상관분석 (Correlation)

두 변수가 얼마나 서로 관계가 있는지 알아보는 방법으로, 두 수치가 모두 숫자로 이루어져 있을 때 두 변수 사이에 여러 관계가 관찰될 수 있다.

- `df.corr()` : 피어슨의 상관관계 계수 구하기
- `df.corr(method = 'spearman')` : 스피어만의 상관관계 계수 구하기

- 특정 행에 대한 상관관계를 보고싶을 때 아래와 같이 명령함

    `df.행이름1.corr(df.행이름2)`

## 3. statsmodels를 이용한 회귀분석 (Regression) *매우 중요

독립변수와 종속변수 사이의 상관관계를 분석하는 방법으로, 독립변수 하나가 종속변수 하나에 연관이 되는지 또는 독립변수 여러개가 상호작용하여 종속변수 하나에 연관이 되는지 알아볼 수 있다.

(1) 단순회귀모델(simple regression model) : 종속변수 하나, 독립변수 하나

(2) 다중회귀모델(multiple regression model) : 종속변수 하나, 독립변수 여러개

### 1) statsmodels 설치 및 불러오기

```python
# 회기분석을 위해 'statsmodels'를 설치한다
pip install statsmodels
```

```python
# statsmodels 중 회귀분석할 수 있는 formula.api를 불러올 것
import statsmodels.formula.api as smf
```

### 2) 회기분석하기

- ols() 함수 : 회기분석할 수 있는 함수
- 단순회귀모델 (simple regression model)

    `ols(formula = '종속변수 ~ 독립변수', data = 데이터프레임이름)`

    ```python
    model = smf.ols(formula = 'jobSatisfaction ~ English', data = df)
    ```

- 다중회귀모델 (multiple regression model)

    `ols(formula = '종속변수 ~ 독립변수1 + 독립변수2 + 독립변수3', data = 데이터프레임이름)`

    ```python
    model_multiple = smf.ols(formula = 'jobSatisfaction ~ English + stress + income', data = df2)
    ```

- 회귀분석 결과 확인하기

    ```python
    # 결과를 새로운 변수로 저장
    result = model.fit()

    # 변수명.summary()
    print(result.summary())
    ```