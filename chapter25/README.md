# 클래스

- 파스칼 케이스를 사용하는것이 일반적이다.
- 클래스는 클래스 정의 이전에 참조할 수 없다.
- 클래스는 생성자 함수이며 new 연산자와 함께 호출되어 인스턴스를 생성한다.

##### 클래스와 생성자 함수의 차이점

1. 클래스는 new연산자없이 호출하면 에러가 발생한다. 하지만 생성자 함수를 new 연산자 없이 호출하면 일반 함수로서 호출된다.
2. 클래스는 상속을 지원하는 extends와 super 키워드를 제공한다. 하지만 생성자 함수는 extends와 super 키워드를 지원하지 않는다.
3. 클래스는 호이스팅이 발생하지 않는것처럼 동작한다. 하지만 함수 선언문으로 정의된 생성자 함수는 함수 호이스팅이, 함수 표현식으로 정의한 생성자 함수는 변수 호이스팅이 발생한다.
4. 클래스 내의 모든 코드에는 암묵적으로 strict mode가 지정되어 실행되며 strict mode를 해제할 수 없다. 하지만 생성자 함수는 암묵적으로 strict mode가 지정되지 않는다.
5. 클래스의 constructor, 프로토타입 메서드, 정적 메서드는 모두 프로퍼티 어트리뷰트 \[[Enumerable]]의 값이 false다. 다시 말해 열거되지 않는다.

## 메서드

- 클래스 몸체에 정의할 수 있는 메서드는 constructor(생성자), 프로토타입 메서드, 정적 메서드 세가지가 있다.

##### constructor

- constructor는 인스턴스를 생성하고 초기화하기 위한 특수한 메서드다.
- constructor는 이름을 변경할 수 없다.
- 클래스내의 최대 한 개만 존재할 수 있다.
- constructor는 생략할 수 있다.
- constructor는 별도의 반환문을 갖지 않는다.

##### 프로토타입 메서드

- 클래스 몸체에서 정의한 메서드는 생성자 함수에 의한 객체 생성 방식과는 다르게 클래스의 prototype 프로퍼티에 메서드를 추가하지 않아도 기본적으로 프로토타입 메서드가 된다.

##### 정적 메서드

- 인스턴스를 생성하지 않아도 호출할 수 있는 메서드를 말한다.
- 클래스에서는 메서드에 static 키워드를 붙이면 정적 메서드가 된다.

##### 정적 메서드와 프로토타입 메서드의 차이

1. 정적 메서드와 프로토타입 메서드는 자신이 속해 있는 프로토타입 체인이 다르다.
2. 정적 메서드는 클래스로 호출하고 프로토타입 메서드는 인스턴스로 호출한다.
3. 정적 메서드는 인스턴스 프로퍼티를 참조할 수 없지만 프로토타입 메서드는 인스턴스 프로퍼티를 참조할 수 있다.

##### 클래스에서 정의한 메서드의 특징

1. function 키워드를 생략한 메서드 축약 표현을 사용한다.
2. 객체 리터럴과는 다르게 클래스에 메서드를 정의할 때는 콤마가 필요없다.
3. 암묵적으로 strict mode가 실행된다.
4. for..in문이나 Object.keys 메서드 등으로 열거할 수 없다. 즉, 프로퍼티의 열거 기능 여부를 나타내며 불리언 값을 갖는 프로퍼티 어트리뷰트 \[[Enumerable]]의 값이 false다.
5. 내부 메서드 \[[Construct]]를 갖지 않는 non-constructor다. 따라서 new 연산자와 함께 호출할 수 없다.

## 클래스의 인스턴스 생성 과정

1. 인스턴스 생성과 this 바인딩
2. 인스턴스 초기화
3. 인스턴스 반환

## 프로퍼티

##### 인스턴스 프로퍼티

- 인스턴스 프로퍼티는 constructor 내부에서 정의해야 한다.

##### 접근자 프로퍼티

- 접근자 프로퍼티는 자체적으로는 값을 갖지 않고 다른 데이터 프로퍼티의 값을 읽거나 저장할 때 사용하는 접근자 함수, 즉 getter 함수와 setter 함수로 구성되어 있다.

##### 클래스 필드 정의 제안

- 클래스 필드는 클래스 기반 객체지향 언어에서 클래스가 생성할 인스턴스의 프로퍼티를 가리키는 용어다.
- 클래스 몸체에서 클래스 필드를 정의할 수 있는걸 클래스 필드 정의 제안이라고 한다.

##### private 필드 정의 제안

- private 필드의 선두에는 #을 붙여준다. private 필드를 참조할 때도 #을 붙여주어야한다.
- private 필드는 클래스 내부에서만 참조할 수 있다.
- private 필드는 반드시 클래스 몸체의 정의해야 한다. private 필드를 직접 constructor에 정의하면 에러가 발생한다.

## 상속애 의한 클래스 확장

##### 클래스 상속과 생성자 함수 상속

- 상속에 의한 클래스 확장은 기존 클래스를 상속받아 새로운 클래스를 확장하여 정의하는 것이다.
- 상속을 통해 클래스를 확장하려면 extends 키워드를 사용하여 상속받을 클래스를 정의한다.

##### 동적 상속

- extends 키워드는 클래스뿐만 아니라 생성자 함수를 상속받아 클래스를 확장할 수도 있다. 단, extends 키워드 앞에는 반드시 클래스가 와야 한다.
- extends 키워드 다음에는 클래스뿐만이 아니라 \[[Construct]] 내부 메서드를 갖는 함수 객체로 평가될 수 있는 모든 표현식을 사용할 수 있다. 이를 통해 동적으로 상속받을 대상을 결정할 수 있다.

##### super 키워드

- super를 호출하면 수퍼클래스의 constructor를 호출한다.
- super를 참조하면 수퍼클래스의 메서드를 호출할 수 있다.
- super를 호출할 때 주의할 사항
  1. 서브클래스에서 constructor를 생략하지 않는 경우 서브클래스의 constructor에서는 반드시 super를 호출해야한다.
  2. 서브클래스의 constructor에서 super를 호출하기 전에는 this를 참조할 수 없다.
  3. super는 반드시 서브클래스의 constructor에서만 호출한다. 서브클래스가 아닌 클래스의 constructor나 함수에서 super를 호출하면 에러가 발생한다.
- 메서드 내에서 super를 참조하면 수퍼클래스의 메서드를 호출할 수 있다.

##### 상속 클래스의 인스턴스 생성 과정

1. 서브클래스의 super 호출
   > 서브클래스는 자신이 직접 인스턴스를 생성하지 않고 수퍼클래스에게 인스턴스 생성을 위임한다. 이것이 바로 서브클래스의 constructor에서 반드시 super를 호출해야 하는 이유다.
2. 수퍼클래스의 인스턴스 생성과 this 바인딩
3. 수퍼클래스의 인스턴스 초기화
4. 서브클래스 constructor로의 복귀와 this 바인딩
5. 서브클래스의 인스턴스 초기화
6. 인스턴스 반환