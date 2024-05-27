# ES6 함수의 추가 기능

## 함수의 구분

- ES6 이전의 모든 함수는 일반 함수로서 호출할 수 있는 것은 물론 생성자 함수로서 호출할 수 있다.

## 메서드

- ES6 사양에서 메서드는 메서드 축약 표현으로 정의된 함수만을 의미한다.
- ES6 사양에서 정의한 메서드는 인스턴스를 생성할 수 없는 non-constructor다. 따라서 ES6 메서드는 생성자 함수로서 호출할 수 없다.
- ES6 메서드는 자신을 바인딩한 객체를 가리키는 내부 슬롯 \[[HomeObject]]를 갖는다.

## 화살표 함수

- 화살표 함수는 함수 선언문으로 정의할 수 없고 함수 표현식으로 정의해야 한다. 호출 방식은 기존 함수와 동일하다.

##### 매개변수 선언

- 매개변수가 한 개인 경우 소괄호()를 생략할 수 있다.
- 매개변수가 없는 경우 소괄호()를 생략할 수 없다.

##### 함수 몸체 정의

- 함수 몸체가 하나의 문으로 구성된다면 함수 몸체를 감싸는 중괄호 {}를 생략할 수 있다. 이때 함수 몸체 내부의 문이 값으로 평가될 수 있는 표현식인 문이라면 암묵적으로 반환된다.
  > 함수 몸체의 문이 표현식이 아닌 문이라면 중괄호를 생략할 수 없다.
- 객체 리터럴을 반환하는 경우 객체 리터럴을 소괄호 ()로 감싸줘야 한다.
  > 객체 리터럴을 소괄호 ()로 감싸지 않으면 객체 리터럴의 중괄호{}를 함수 몸체를 감싸는 중괄호{}로 잘못 해석한다.
- 화살표 함수도 즉시 실행 함수로 사용할 수 있다.

##### 화살표 함수와 일반 함수의 차이

1. 화살표 함수는 인스턴스를 생성할 수 없는 non-constructor이다
   > 화살표 함수는 인스턴스를 생성할 수 없으므로 prototype 프로퍼티가 없고 프로토타입도 생성하지 않는다.
2. 중복된 매개변수 이름을 선언할 수 없다.
3. 화살표 함수는 함수 자체의 this, arguments, super, new.target 바인딩을 갖지 않는다.
   > 스코프 체인상에서 가장 가까운 상위 함수 중에서 화살표 함수가 아닌 함수의 this, arguments, super, new.target을 참조한다.

##### this

- 화살표 함수는 함수 자체의 this 바인딩을 갖지 않는다. 따라서 화살표 함수 내부에서 this를 참조하면 상위 스코프의 this를 그대로 참조한다. 이를 lexical this라 한다.
- 메서드를 화살표 함수로 정의하는 것은 피해야 한다.

##### super

- 화살표 함수는 함수 자체의 super 바인딩을 갖지 않는다. 따라서 화살표 함수 내부에서 super를 참조하면 this와 마찬가지로 상위 스코프의 super를 참조한다.

##### arguments

- 화살표 함수는 함수 자체의 arguments 바인딩을 갖지 않는다. 따라서 화살표 함수 내부에서 arguments를 참조하면 this와 마찬가지로 상위 스코프의 arguments를 참조한다.

## Rest 파라미터

- Rest 파라미터(나머지 매개변수)는 매개변수 이름 앞에 세개의 점 ...을 붙여서 정의한 매개변수를 의미한다.
- Rest 파라미터는 함수에 전달된 인수들의 목록을 배열로 전달받는다.
- Rest 파라미터는 반드시 마지막 파라미터이어야 한다.
- REST 파라미터는 단 하나만 선언할 수 있다.

## 매개변수 기본값
- 매개변수 기본값은 매개변수에 인수를 전달하지 않은 경우와 undefined를 전달한 경우에만 유효하다.
- Rest 파라미터에는 기본값을 지정할 수 없다.