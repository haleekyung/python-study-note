## 반복문 축약
### 리스트 안에 for문 쓰기
* 기본 문법
* 맨 앞에 있는 ```액션```이 반환하는 최종 데이터라고 보면 됨
```python
변수명 = [액션 for 반복문]
```

* 다양한 상황
* ```n```이 최종 데이터임
```python
my = [n for n in range(1, 6)]
print(my)
```

* ```i * i``` 가 최종데이터
```python
array = [i * i for i in range(0, 20, 2)] # 최종결과인 i * i를 넣음
print(array)
```

* ```x[:-1]```가 최종 데이터
```python
character = [x[:-1] for x in list(set(re.findall(r'[A-Z][a-z]+:', script101)))]
print(character)
```
