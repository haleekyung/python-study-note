# Numpy
넘파이는 배열(array)을 다루는 프로그램이며, 큰 데이터를 다룰 때 진가를 발휘한다. 
예를 들어 엄청나게 많은 데이터 중에서 700이 넘는 숫자만 찾아서 참(True)로 변환한다거나, 특정한 행이나 열에 있는 정보만 반올림하거나 버림하기도 쉽다. 또한 복잡한 배열 연산도 가능하다.

## 배열 정의하기 : import numpy as np
우선 numpy를 np로 키워드 축약한다.

## 배열 슬라이싱
우선 배열 먼저한다.
```python
a = np.array([[1, 2, 3], [1, 3, 4]])
```

이후 그 중 일부만 슬라이싱 한다.
```python
a[1], [2]   
a[1, 2] # 위와 같은 값을 가지나 다른 표기를 할 수도 있다.
a[1:, 2:] # 여기서도 ':(숫자 이후 값)'에 대한 적용이 먹힌다.
```

## shape : 배열 크기 알아내기
해당 변수의 배열 행렬이 어떻게 이루어져있는지 숫자로 표현함
```python
e = np.array([[2, 3, 4, 5], [3, 4, 5, 6]])
e.shape # 2, 4
```

## dtype : 원소 유형 확인
```python
e.dtype # int64로 표현
```

|원소유형|표기법|
|---|---|
|부호가 있는 정수|int(32, 64)|
|부호가 없는 정수|unit(32, 64)|
|실수|float(32, 64)|
|복소수|complex|
|불(참, 거짓을 가지는 자료)|bool|
|문자열|string|
|파이썬 오브젝트|object|
|유니코드|unicode|

## astype : 데이터 타입 바꾸기
* 이전에 개인적으로 'usecsv'의 switch() 모듈을 만들어서 하기보다 넘파이의 astype을 쓰면 더 쉽게 작업할 수 있다.
```python
data = np.arange(1, 5) # 1부터 4까지로 이루어진 배열 만들기
data.astype('float64') # float64 정수로 바뀜
data.astype('int64') # int64 로 바뀜
```

## 넘파이 함수들
* 0으로 이루어진 함수 : np.zeros()
    ```python
    np.zeros((2, 10))
    ```
* 1로 이루어진 배열 만들기 : np.ones()
    ```python
    np.ones((2, 10))
    ```
* 연속형 함수 만들기 : np.arange()
    ```python
    np.arange(2, 10)
    ```
* 행과 열 바꾸기 : np.transpose()
    ```python
    a = np.ones((2, 3))
    b = np.transpose(a)
    ```
  
## 배열 사칙연산 시 주의할 점
* 배열은 기본적으로 broadcast가 가능하다. 배열이 달라도 사칙연산이 가능하다.
* 그러나 예외적으로 행과 열 모두가 다른 경우 사칙연산을 할 수 없다.