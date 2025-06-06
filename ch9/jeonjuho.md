# 단위 테스트

프로그램이 ‘돌아간다’는 사실만 확인하는 일회성 코드에서 벗어나 
‘제대로 돌아간다’는 것을 확인하도록 테스트 코드를 작성해야 한다.

## TDD 법칙 세 가지

1. 실패하는 단위 테스트를 작성할 때까지 실제 코드를 작성하지 않는다.
2. 컴파일은 실패하지 않으면서 실행이 실패하는 정도로만 단위 테스트를 작성한다.
3. 현재 실패하는 테스트를 통과할 정도로만 실제 코드를 작성한다.

실제 코드와 맞먹을 정도로 방대한 테스트 코드는 심각한 관리 문제를 유발하기도 한다.

## 깨끗한 테스트 코드 유지하기

테스트 코드가 복잡할수록 실제 코드를 짜는 시간보다 기존의 테스트 케이스를 수정하는 시간이 더 필요할 수 있다. 테스트 코드 때문에 개발 속도가 느려진다는 의견이 나올 수 있는 것이다.

그렇기 때문에 실제 코드 못지 않게 테스트 코드를 깨끗하게 짜야 한다.

테스트 커버리지가 높은 테스트를 작성할 수록 실제 코드의 신뢰도가 높아진다. 이는 코드에 유연성,유지보수성, 재사용성을 제공한다고 볼 수 있다. 테스트 케이스가 있기 때문에 변경이 쉬워지기 때문이다.

## 깨끗한 테스트 코드

깨끗한 테스트 코드는 가독성이 높은 코드이다. 가독성을 위해서 테스트 코드는 최소의 표현으로 많은 것을 나타낼 수 있어야 한다.

BUILD-OPERATE-CHECK 패턴을 사용해서 각 부분에서의 역할을 나누어 이해를 돕는다.

테스트 코드에서도 리팩터링을 통해 코드를 간결하고 표현력이 풍부하도록 개선할 필요가 있다.

## 테스트 당 assert 하나

하나의 테스트 코드에 여러 검증이 포함될 때, 각각의 검증을 메서드로 추출하면 결론이 하나라서 코드를 이해하기 쉽고 빠르다. 하지만 이렇게 하면 중복되는 코드가 많아질 수 있다. 이 때, 템플릿 메서드 패턴을 활용하여 given/when 부분을 @Before 함수로 선언해준 후 @Test 함수에 then 만을 두면 중복이 많이 개선된다. 아무래도 복잡성이 증가하니 상황에 따라서 assert 문을 여럿 사용하는 편이 좋을 수 있다.

또한, 테스트 당 개념을 하나만 검증하도록 해야한다. 

## F.I.R.S.T

- Fast
    - 테스트는 자주 실행되어야 하므로 빠르게 실행되어야 한다.
- Independent
    - 각 테스트가 서로를 의존하지 않도록 독립적인 실행 환경을 제공해주어야 한다.
- Repeatable
    - 어떤 환경에서도 반복 가능해야 한다.
- Self-Validating
    - 테스트는 성공 혹은 실패해야 한다.
- Timely
    - 테스트하려는 실제 코드를 구현하기 직전에 구현한다.

## 결론

테스트 코드가 방치되어 망가지면 실제 코드도 망가진다.

테스트 코드를 깨끗하게 유지하자.