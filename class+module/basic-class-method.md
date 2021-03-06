## 클래스 변수와 메소드

클래스도 인스턴스와 마찬가지로 속성(변수)와 기능(함수)를 가질 수 있음

**클래스 변수 만들기**

- class 구문 아래 단계에 변수를 선언하기만 하면 된다.
- 클래스 변수는 일반 변수와 다르지 않게 사용할 수 있다.

```python
class 클래스 이름:
	클래스 변수 = 값
```

**클래스 변수에 접근하기**

```python
클래스이름.변수이름
```

## 클래스 함수

- 클래스 함수도 클래스 변수처럼 클래스가 가진 함수라고 표현할 수 있다.
- 일반적인 함수로 만드나, 클래스 함수로 만드나 사용에는 큰 차이가 없다.
- 생성방법 : 데코레이터(decorator)로 만듬

    @classmethod ← 와 같은 형식

## 클래스 데코레이터

함수나 클래스 앞뒤에 꾸밀 부가적인 내용, 혹은 반복할 내용을 데코레이터로 정의해서 손쉽게 사용할 수 있도록 한 것을 말함

- @ 로 시작하는 것을 파이썬에서는 '데코레이터'라고 말하며, 꾸며주는 것으로 의미를 가짐
- 함수 데코레이터와 다르지 않은 방식으로 클래스 데코레이터를 만듬

```python
# 함수를 이용한 데코레이터
def hello():
	print("hello")

# 위 코드 앞에 "인사가 시작되었습니다." 뒤에 "인사가 종료되었습니다."를 출력하고 싶은 경우
# 아래의 코드를 예제로 구현함

def test(function):
	def wrapper()
		print("인사가 시작되었습니다.")
		function()
		print("인사가 종료되었습니다.")
	return wrapper

# 데코레이터를 붙여 함수 만들기
@test
def hello():
	print("hello")

# 함수 호출하기
hello()
```

```python
# 함수로 데코레이터 만들기
class 클래스 이름:
	@classmethod
	def 클래스 함수(cls, 매개변수):
		pass

# 클래스 함수 호출하기
클래스 이름.함수이름(매개변수)
```