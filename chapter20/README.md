# strict mode

- `strict mode`는 자바스크립트 언어의 문법을 좀 더 엄격히 적용하여 오류를 발생시킬 가능성이 높거나 자바스크립트 엔진의 최적화 작업에 문제를 일으킬 수 있는 코드에 대해 명시적인 에러를 발생시킨다.
- `strict mode`를 적용하려면 전역의 선두 또는 함수 몸체의 선두에 'use strict';를 추가한다.
- 전역에 `strict mode`를 적용하는 것은 피하자
- 함수 단위로 `strict mode`를 적용하는 것도 피하자

## strict mode가 발생시키는 에러

- 암묵적 전역
- 변수, 함수, 매개변수의 삭제
- 매개변수 이름의 중복
- with문의 사용

## strict mode 적용에 의한 변화

- 일반 함수의 this
  > 일반 함수는 this를 사용 할 필요가 없다.
- arguments 객체
  > strict mode에서는 매개변수에 전달된 인수를 재할당하여 변경해도 arguments 객체에 반영되지 않는다.
