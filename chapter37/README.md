# Set과 Map

## Set

- Set 객체는 중복되지 않는 유일한 값들의 집합이다.

##### Set 객체의 생성

- Set 생성자 함수는 이터러블을 인수로 전달받아 Set 객체를 생성한다. 이때 이터러블의 중복된 값은 Set 객체에 요소로 저장되지 않는다.
- 배열에서 중복된 요소를 제거할 수 있다.

##### 요소 개수 확인

- `size` 프로퍼티를 사용한다.
- Set 객체의 요소 개수를 변경할 수 없다.

##### 요소 추가

- `add` 메서드를 사용한다.
- `add` 메서드를 연속적으로 호출할 수 있다.
- 중복된 요소의 추가는 허용되지 않는다.

##### 요소 존재 여부 확인

- `has`메서드를 사용한다.

##### 요소 삭제

- `delete` 메서드를 사용한다.
- 삭제하려는 요소값을 인수로 전달한다.

##### 요소 일괄 삭제

- `clear` 메서드를 사용한다.

##### 집합 연산

- Set 객체는 수학접 집합을 구현하기 위한 자료구조다. 따라서 Set 객체를 통해 교집합, 합집합, 차집합 등을 구현할 수 있다.

## Map

- Map 객체는 키와 값의 쌍으로 이루어진 컬렉션이다.

##### Map 객체의 생성

- Map 생성자 함수는 이터러블을 인수로 전달받아 Map 객체를 생성한다. 이때 인수로 전달되는 이터러블은 키와 값의 쌍으로 이루어진 요소로 구성되어야 한다.
- 중복된 키를 갖는 요소가 존재할 수 없다.

##### 요소 개수 확인

- `size` 프로퍼티를 사용한다.
- Map 객체의 요소 개수를 변경할 수 없다.

##### 요소 추가

- `set` 메서드를 사용한다.
- `set` 메서드를 연속적으로 호출할 수 있다.
- 객체는 문자열 또는 심벌 값만 키로 사용할 수 있다. 하지만 Map 객체는 키 타입에 제한이 없다.

##### 요소 존재 여부 확인

- `has` 메서드를 사용한다.

##### 요소 삭제

- `delete` 메서드를 사용한다.

##### 요소 일괄 삭제

- `clear` 메서드를 사용한다.
