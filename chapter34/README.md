# 이터러블

- 이터러블 프로토콜을 준수한 객체를 이터러블이라 한다. 즉 이터러블은 Symbol.iterator를 프로퍼티 키로 사용한 메서드를 직접 구현하거나 프로토타입 체인을 통해 상속받은 객체를 말한다.

##### 이터레이터

- 이터러블의 Symbol.iterator 메서드를 호출하면 이터레이터 프로토콜을 준수한 이터레이터를 반환한다. 이터러블의 Symbol.iterator 메서드가 반환한 이터레이터는 next 메서드를 갖는다.
- next 메서드를 호출하면 이터러블을 순차적으로 한 단계씩 순회하며 순회 결과를 나타내는 `이터레이터 리절트 객체`를 반환한다.
- 이터레이터 리절트 객체의 `value` 프로퍼티는 현재 순회중인 이터러블의 값을 나타내며 `done` 프로퍼티는 이터러블의 순회 완료 여부를 나타낸다.

## for...of 문

- 이터러블을 순회하면서 이터러블의 요소를 변수에 할당한다.

## 이터러블과 유사 배열 객체

- 유사 배열 객체는 마치 배열처럼 인덱스로 프로퍼티 값에 접근할 수 있고 length 프로퍼티를 갖는 객체를 말한다.
- 유사 배열 객체는 이터러블이 아닌 일반 객체다. 따라서 유사 배열 객체에는 Symbol.iterator 메서드가 없기 때문에 for...of 문으로 순회할 수 없다.

## 이터레이션 프로토콜의 필요성

- 이터레이션 프로토콜은 다양한 데이터 공급자가 하나의 순회 방식을 갖도록 규정하여 데이터 소비자가 효율적으로 다양한 데이터 공급자를 사용할 수 있도록 데이터 소비자와 데이터 공급자를 연결하는 인터페이스 역할을 한다.
