# 비동기 프로그래밍

- 자바스크립트 엔진은 싱글 스레드로 동작하지만 브라우저는 멀티 스레드로 동작한다.

## 동기 처리와 비동기 처리

- 현재 실행 중인 태스크가 종료할 때까지 다음에 실행될 태스크가 대기하는 방식을 `동기 처리`라고 한다.
- 현재 실행 중인 태스크가 종료되지 않은 상태라 해도 다음 태스크를 곧바로 실행하는 방식을 `비동기 처리`라고 한다.

## 이벤트 루프와 태스크 큐

- 자바스크립트의 동시성을 지원하는 것이 바로 `이벤트 루프`다.
- `태스크 큐` - setTimeout이나 setInterval과 같은 비동기 함수의 콜백 함수 또는 이벤트 핸들러가 일시적으로 보관되는 영역이다.
- `이벤트 루프` - 콜 스택이 비어 있고 태스크 큐에 대기 중인 함수가 있다면 이벤트 루프는 순차적으로 태스크 큐에 대기 중인 함수를 콜 스택으로 이동시킨다.