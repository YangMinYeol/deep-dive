# 에러 처리

## try...catch...finally 문

- finally문은 불필요하다면 생략 가능하다. catch문도 생략 가능하지만 catch문이 없는 try문은 의미가 없으므로 생략하지 않는다.

```javascript
try {
  // 실행할 코드(에러가 발생할 가능성이 있는 코드)
} catch (err) {
  // try 코드 블록에서 에러가 발생하면 이 코드 블록의 코드가 실행된다.
  // err에는 try 코드 블록에서 발생한 Error 객체가 전달된다.
} finally {
  // 에러 발생과 상관없이 반드시 한 번 실행된다.
}
```

## Error 객체

- Error 생성자 함수는 에러 객체를 생성한다. Error 생성자 함수에는 에러를 상세히 설명하는 에러 메시지를 인수로 전달할 수 있다.
- Error 생성자 함수가 생성한 에러 객체는 message 프로퍼티와 stack 프로퍼티를 갖는다.
  | 생성자 함수 | 인스턴스 |
  |---| ---|
  | Error| 일반적 에러 객체|
  | SyntaxError| 자바스크립트 문법에 맞지 않는 문을 해석할 때 발생하는 에러 객체|
  | ReferenceError| 참조할 수 없는 식별자를 참조했을 때 발생하는 에러 객체|
  | TypeError| 피연산자 또는 인수의 데이터 타입이 유효하지 않을 때 발생하는 에러 객체|
  | RangeError| 숫자값의 허용 범위를 벗어났을 때 발생하는 에러 객체|
  | URIError| encodeURI 또는 decondeURI 함수에 부적절한 인수를 전달했을 때 발생하는 에러 객체|
  | EvalError| eval 함수에서 발생하는 에러 객체|
