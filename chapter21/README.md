# 빌트인 객체

## 표준 빌트인 객체

- 자바스크립트 실행 환경과 관계없이 언제나 사용할 수 있다.
- 표준 빌트인 객체는 전역 객체의 프로퍼티로서 제공된다. 따라서 별도의 선언 없이 전역 변수처럼 언제나 참조할 수 있다.

## 호스트 객체

- 자바스크립트 실행 환경에서 추가로 제공하는 객체를 말한다.

## 사용자 정의 객체

- 사용자 정의 객체는 표준 빌트인 객체와 호스트 객체처럼 기본 제공되는 객체가 아닌 사용자가 직접 정의한 객체를 말한다.

## 원시값과 래퍼 객체

- 문자열, 숫자, 불리언 값에 대해 객체처럼 접근하면 생성되는 임시 객체를 래퍼 객체라 한다.

## 전역 객체

- 코드가 실행되기 이전 단계에 자바스크립트 엔진에 의해 어떤객체보다도 먼저 생성되는 특수한 객체이며, 어떤 객체에도 속하지 않은 최상위 객체다.
  > 브라우저 환경에서는 `window`, Node.js에서는 `global`, 둘 다 사용가능한 `globalThis`도 있다.
- 전역 객체는 개발자가 의도적으로 생성할 수 없다. 즉, 전역 객체를 생성할 수 있는 생성자 함수가 제공되지 않는다.
- 전역 객체의 프로퍼티를 참조할 때 window(또는 global)를 생략할 수 있다.
- 브라우저 환경에서는 Web API를 호스트 객체로 제공하고 Node.js환경에서는 Node.js 고유의 API를 호스트 객체로 제공한다.
- var 키워드로 선언한 전역 변수와 선언하지 않은 변수에 값을 할당한 암묵적 전역, 그리고 전역 함수는 전역 객체의 프로퍼티가 된다.(let, const 제외)

##### 빌트인 전역 프로퍼티

- 빌트인 전역 프로퍼티는 전역 객체의 프로퍼티를 의미한다.
- `Infinity` - 무한대를 나타내는 숫자값 Infinity를 갖는다.
- `NaN` - 숫자가 아님을 나타내는 숫자값 NaN을 갖는다.
- `undefined` - 원시 타입 undefined를 갖는다.

##### 빌트인 전역 함수

- 빌트인 전역 함수는 애플리케이션 전역에서 호출할 수 있는 빌트인 함수로서 전역 객체의 메서드다.
- `eval` - 자바스크립트 코드를 나타내는 문자열을 인수로 전달받는다.
  > `eval` 함수의 사용은 금지해야 한다. 이유와 해결법은 필요시 찾아보자.
- `isFinite` - 전달받은 인수가 정상적인 유한수인지 검사하여 유한수이면 `true`, 무한수면 `false`를 반환한다.
- `isNaN` - 전달받은 인수가 NaN인지 검사하여 그 결과를 불리언 타입으로 반환한다.
- `parseFloat` - 전달받은 문자열 인수를 부동 소수점 숫자, 즉 실수로 해석하여 반환한다.
- `parseInt` - 전달받은 문자열을 정수로 해석하여 반환한다.

##### encodeURI/decodeURI

- `encodeURI` 함수는 완전한 URI를 문자열로 전달받아 이스케이프 처리를 위해 인코딩한다.
- `decodeURI` 함수는 인코딩된 URI를 인수로 전달받아 이스케이프 처리 이전으로 디코딩한다.

##### encodeURIComponent/decodeURIComponent

- `encodeURIComponent` 함수는 URI 구성 요소를 인수로 전달받아 인코딩한다.
- `decodeURIComponent` 함수는 매개변수로 전달된 URI 구성 요소를 디코딩한다.
