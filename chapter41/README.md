# 타이머

## 호출 스케줄링

- 함수를 명시적으로 호출하지 않고 일정 시간이 경과된 이후에 호출되도록 함수 호출을 예약하려면 타이머 함수를 사용한다. 이를 `호출 스케줄링`이라 한다.
- `setTimeout` 함수가 생성한 타이머는 단 한 번 동작하고, `setInterval` 함수가 생성한 타이머는 반복 동작한다.
- `setTimeout` 과 `setInterval`은 `비동기 처리 방식`으로 동작한다.

## 타이머 함수

- 첫 번째 인수는 콜백함수 두 번째 인수는 시간을 전달받는다.
- 세 번째 이후 인수는 콜백 함수에 전달할 파라미터가 된다.
- 생성한 타이머를 식별할 수 있는 고유한 타이머 id를 반환한다.
- 타이머 id를 이용하여 타이머를 취소할 수 있다.

## 디바운스와 스로틀

- 디바운스와 스로틀은 짧은 시간 간격으로 연속해서 발생하는 이벤트를 그룹화해서 과도한 이벤트 핸들러의 호출을 방지하는 프로그래밍 기법이다.
- 첫 번째 인수에는 콜백 함수, 두 번째 인수에는 시간을 의미한다.
- 두 번째 인수로 전달한 시간 보다 짧은 간격으로 이벤트가 발생하면 이전 타이머를 취소하고 새로운 타이머를 재설정한다.

##### 디바운스

- 디바운스는 짧은 시간 간격으로 발생하는 이벤트를 그룹화해서 마지막에 한 번만 이벤트 핸들러가 호출되도록 한다.
- 실무에서는 Underscore의 debounce 함수나 Lodash의 debounce 함수를 사용하는 것을 권장한다.

##### 스로틀

- 스로틀은 짧은 시간 간격으로 이벤트가 연속해서 발생하더라도 일정 시간 간격으로 이벤트 핸들러가 최대 한 번만 호출되도록 한다.
- 실무에서는 Underscore의 throttle 함수나 Lodash의 throttle 함수를 사용하는 것을 권장한다.
