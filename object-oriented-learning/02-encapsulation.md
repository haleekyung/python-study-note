# 캡슐화(Encapsulation)
* 데이터와 관련 기능을 묶기 : 데이터 구현과 관련된 상세 내용은 그 정보를 외부에 감추도록 하고, 내부에서만 확인할 수 있게 한다. 캡슐화는 정보은닉을 포함하기도 한다.
* 왜 캡슐화를 하나? : 외부에 영향 없이 객체 내부 구현의 변경 가능

***

## 캡슐화하지 않을 경우
* 요구사항이 바뀌어서 데이터의 사용에 변화가 생기는 경우 문제 발생


* 요구사항 변경 예
  * Date를 LocalDateTime으로 변경해야 한다
  * 계정을 차단하면 모든 실행 권한 없음


## 캡슐화하면
* 요구사항의 변화가 있을 때 연쇄적으로 변경이 전파되는 것을 최소화할 수 있다.

* 캡슐화를 하면 기능에 대한(의도) 이해를 높일 수 있다.

```java
if (acc.hasRegularPermission()) {
.. 정회원 기능
}
```

```java
public class Account {
    public boolean hasRegularPermission(){
        return membership == REGULAR &&
            (expDate.isAfter(now()) ||
                (
                serviceDate.isBefor(fiveYearAgo()) &&
                addMonth(expDate).isAfter(now())
            )
        );
}
```
-> 내부 구현만 바뀌고, 그 기능을 사용하는 다른 코드는 바뀌지 않는다.

## 캡슐화의 원칙
* Tell, Don't Ask
  * 해달라고 요청하지 않고 '말하라'

```python
# Don't ask

if acc.getMembership() == REGULAR):
...
```

```python
# Tell

if acc.hasRegularPermission():
...

```

* Demeter's Law
  * 메서드에서 생성한 객체의 메서드만 호출해라
  * 파라미터로 받은 객체의 메서드만 호출해라
  * 필드로 참조하는 객체의 메서드만 호출해라

```python
# not good

acc.getExpDate().isAfter(now)

Date = acc.getExpDate()
date.isAfter(now):
```
```python
# good

acc.isExpired()
acc.isValid(now)
```
