## import os

```python
import os
```

### os 모듈 관련 명령어

- os.getcwd() : 현재 위치 확인하기
- os.chdir() : 폴더 이동하기, 여기서는 역슬레시를 각각 하나씩 더 붙여줘야 함
    - 역슬레시 붙이기 싫으면 아래와 같이 작성할 것.

    ```python
    import os
    	os.chdir(r'C\Users\PC\Onedrive - Office Everyday\MyScript\python\manuscript_Book\Planning')
    ```

    - 경로 코드 갚에 r을 인식하면 \를 특수문자로 인식하지 않아서 두 번 쓰지 않아도 됨
- os.listed() : 폴더 안의 파일 확인하기
    - 리스트로 만들고 싶을 경우 아래와 같이 작성

    ```python
    folderFile = os.listdir() # 변수로 저장
    print(folderFile) # 출력하면 리스트로 출력, 타입이 리스트기 때문
    ```

- open() : 파일 열기

    ```python
    f = open('a.txt', 'w')
    ```

    - 'w' : 쓰기
    - 'r' : 읽기
    - 'a' : 수정하기
    - f.close() : 닫기, 필수로 닫아야 함
- with 문

    ```python
    with open(파일 이름, 파일 열기모드) as f:
    	f에 수행할 명령
    ```

### 한글파일 오류 해결하기

한글파일 오류는 보통 코덱의 문제로 오류를 일으키는 경우가 많음

- f = open('한글파일.txt', 'r')에 encoding = 'utf8' 추가

    ```python
    f = open('한글파일.txt', 'r', encoding = utf8)
    ```

- codecs 모듈 사용

    ```python
    f = codecs.open('한글파일.txt', 'r', 'utf-8')
    f.read()[:10]
    ```