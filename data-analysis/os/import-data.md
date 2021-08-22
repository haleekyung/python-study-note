## 데이터를 OS에서 불러오기
### 데이터 불러오는 모듈
```python
import os, re
```

### chdir : 경로 불러오기
```python
os.chdir(r'경로')
```

### 파일 열기, 닫기, 읽기
* 열기(읽기)
```python
f = open('파일명', 'r', encoding = 'utf-8')
```
* 쓰기
```python
f.write(변수)
```
* 닫기 : 열거나 파일에 텍스트를 작성하고 나면 무조건 닫기 함수 실행할 것
```python
f.close()
```