## 오류가 나는 이유?
1. 구문오류 (syntax error) : 괄호의 갯수, 들여쓰기 문제로 인해 프로그램이 실행되기 전에 발생하는 오류코드
2. 예외(exception) : 프로그램 실행 중 발생하는 오류 의미 (NameError...)
   * 예외해결 : exception handling
        * 조건문 사용하기 : 기본 예외처리, 예외처리 관련 코드 작성문 볼 것 (book_06_1)
        * try 구문 사용하기 : book_06_1 참조
3. 런타임 오류(runtime error) : 

## EOL : End of Line
* 라인 마지막 줄에 문제가 있다

## NameError
* 이름을 제대로 정해주지 않았을 때 발생

## iterable
* 의미: member를 하나씩 차례로 반환 가능한 object를 말함. iterator로 변환이 가능함
* 반복 가능한 객체. 대표적인 타입으로는 list, dict, set, str, bytes, tuple, range ...
* 반복할 수 있다. 정도로 생각할 수 있다.

### Iterable 
* 데이터의 흐름 (stream)을 의미

### StopIteration
* next() 함수를 호출한 이후 yield 키워드를 만나지 못하고 함수가 끝났을 때 예외 발생