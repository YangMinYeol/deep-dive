# 생성자 함수에 의한 객체 생성

## Object 생성자 함수

- 자바스크립트는 Object 생성자 함수 이외에도 String, Number, Boolean, Function, Array, Date, RegExp, Promise등의 빌트인 생성자 함수를 제공한다.
- Object 생성자 함수를 사용해 객체를 생성하는 방식은 특별한 이유가 없다면 그다지 유용하지 않다.

## 생성자 함수

- `생성자 함수`란 new 연산자와 함께 호출하여 객체(인스턴스)를 생성하는 함수를 말한다. 생성자 함수에 의해 생성된 객체를 `인스턴스`라 한다.
- new 연산자와 함께 호출하면 해당 함수는 생성자 함수로 동작한다. 만약 new 연산자와 함께 생성자 함수를 호출하지 않으면 생성자 함수가 아니라 일반 함수로 동작한다.

##### 객체 리터럴에 의한 객체 생성 방식의 문제점

- 동일한 프로퍼티를 갖는 객체를 여러 개 생성해야 하는 경우 매번 같은 프로퍼티를 기술해야 하기 때문에 비효율적이다.

##### 생성자 함수에 의한 객체 생성 방식의 장점

- 프로퍼티 구조가 동일한 객체 여러개를 간편하게 생성할 수 있다.

##### 생성자 함수의 인스턴스 생성 과정

1. 인스턴스 생성과 this 바인딩
2. 인스턴스 초기화
3. 인스턴스 반환

##### 함수객체

- 함수 객체는 callable이면서 constructor이거나 callable이면서 non-constructor다. 즉 모든 함수 객체는 호출할 수 있지만 모든 객체를 생성자 함수로서 호출할 수 있는 것은 아니다.

##### constructor와 non-constructor의 구분

- 함수 객체를 생성할 때 함수 정의 방식에 따른 함수를 constructor와 non-constructor로 구분한다.
- `constructor` - 함수 선언문, 함수 표현식, 클래스
- `non-constructor` - 메서드, 화살표 함수

##### new 연산자

- new 연산자와 함께 함수를 호출하면 해당 함수는 생성자 함수로 동작한다.
- new 연산자와 함께 호출하는 함수는 non-constructor가 아닌 constructor이어야 한다.

##### new.target

- new 연산자와 함께 생성자 함수로서 호출되면 함수 내부의 new.target은 함수 자신을 가리킨다. new 연산자 없이 일반 함수로서 호출된 함수 내부의 new.target은 undefined이다.
