# 판다스(Pandas)
파이썬 환경에서 사용하는 패키지중 하나, 데이터 처리에 최적화된 패키지라고 할 수 있다.

## 데이터프레임이란
데이터프레임(Dataframe)이란 데이터를 쉽게 가공하기 위한 일종의 틀이라고 할 수 있는데, DataFrame()함수를 이용하면 딕셔너리형 자료를 판다스 스스로 가공할 수 있는 데이터프레임으로 만들 수 있다.

따라서 CSV를 불러올 때 판다스를 이용할 때 데이터프레임으로 바꾼 여러가지 방식으로 가공할 수 있다.

pandas를 불러올 때 pip install 하여 불러온 다음, pandas를 'pd'로 축약한 다음 시작한다.
```python
pip install pandas
import pandas as pd
```

## 판다스 이용 함수 (기본)
### sum() : 합계
```python
변수명.sum()
```


### mean() : 평균
```python
변수명.mean()
```

### 데이터 선택하기
인덱스에 있는 key값을 변수 다음에 작성하여 입력
```python
변수명.key값

# 예시
df.age
df.['age'] # 이 표현식도 유효함
```

### read_csv : pandas로 csv 불러오기

```python
import pandas as pd
변수 = pd.read_csv('파일명.csv')
```

### 