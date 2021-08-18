## 제목 행을 50자로 제한

- 짧고 읽기 쉽게, 간결하게 표현

## 제목 첫 첫글자는 대문자로 시작

- read file modification (X)
- Read file modification (O)

## 행 끝에 마침표 넣지 않기

- Open the door.(X)
- Open the door

## 명령문 사용, 현재형으로 사용하지 않기

- Clean your room
- Close the door
- Take out the trash

## 어떻게보다는 '무엇'과 '왜'를 중심으로

## 좋은 커밋 메세지를 위한 영어

[참고 웹사이트 → 클릭하면 이동함](https://blog.ull.im/engineering/2019/03/10/logs-on-git.html)

- 관사 사용하지 않기
- 동명사보다는 명사 사용하기
- 부정문 `**Don't**` 사용하기
- 오타수정은 **Fix typo** 라고 하면 됨

### 커밋 유형 지정

- Feat : 새로운 기능 추가
- Add : 코드나 테스트, 예제, 문서 등의 추가
    - Add A : A를 추가함
    - Add A for B : B를 위해 A를 추가함
    - Add A to B : B에 A를 추가함
- Remove : 코드 삭제 시 사용, Clean이나 Eliminate 사용하기도 함
    - ‘unnecessary’, ‘useless’, ‘unneeded’, ‘unused’, ‘duplicated’이 A 앞에 들어감
    - Remove A : A를 삭제함
    - Remove A from B : B에서 A를 삭제함
- Fix : 버그 수정
    - Fix A in B : B의 A를 수정함
    - Fix A which B, Fix A that B : B절인 A를 수정함
    - Fix A to B, Fix A to be B : B를 위해 A를 수정함
    - Fix A so that B  : A를 수정해서 B가 되었음
    - Fix A where B : B처럼 발생하는 A를 수정함

    → A에는 보통 ‘issue’, ‘error’, ‘crash’ 가 들어감

    ```
    Fix case where content of inline views didn't get relaid out
    Fix case where inline view is visible even though it should have been truncated
    Fix issue where Image.resizeMode isn't respected while source is loading, resulting in unexpected padding
    ```

- Docs : 문서 수정
- Style : 스타일 관련 기능 (코드 포맷팅, 세미콜론 누락, 코드 자체의 변경이 없는 경우)
- Refactor : 코드 리펙토링, 전면 수정 시 사용함
- Simplify : 복잡한 코드를 단순화 할 때 사용
- Test : 테스트 코드, 리펙토링 테스트 코드 추가
- Update : 개정이나 버전 업데이트
- Revise : Update와 비슷하나, 문서 개정이 있을 때 사용
- Correct : 문법 오류나 타입 변경, 이름 변경 등에 사용
- improve : 향상이 있을 때 사용함, 호환성, 테스트 커버리지, 성능, 검증 기능, 접근성 등
- Chore : 빌드 업무 수정, 패키지 매니지 수정 (ex .gitignore 수정)
- Move : 코드 이동 시
- Rename : 이름 변경
- Set : 변수값 변경 등 작은 수정