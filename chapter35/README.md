# 스프레드 문법

- ES6에서 도입된 스프레드 문법(전개 문법) ...은 하나로 뭉쳐 있는 여러 값들의 집합을 펼쳐서 개별적인 값들의 목록으로 만든다.
- 스프레드 문법을 사용할 수 있는 대상은 Array, String, Map, Set, DOM 컬렉션(NodeList, HTMLCollection), arguments와 같이 for...of 문으로 순회할 수 있는 이터러블에 한정된다.
- 스프레드 문법의 결과물은 값으로 사용할 수 없고, 다음과 같이 쉼표로 구분한 값의 목록을 사용하는 문맥에서만 사용할 수 있다.
  1. 함수 호출문의 인수 목록
  2. 배열 리터럴의 요소 목록
  3. 객체 리터럴의 프로퍼티 목록

## 함수 호출문의 인수 목록에서 사용하는 경우

```javascript
const arr = [1, 2, 3];

const max = Math.max(...arr);
```

## 배열 리터럴 내부에서 사용하는 경우

##### concat

```javascript
const arr = [...[1, 2], ...[3, 4]];
```

##### splice

```javascript
const arr1 = [1,2];
const arr2 = [3,4];
arr1.splice(1,0 ...arr2);
```

##### 배열 복사

```javascript
const origin = [1, 2];
const copy = [...origin];
```

## 객체 리터럴 내부에서 사용하는 경우

```javascript
const merged = { x: 1, y: 2, ...{ a: 3, b: 4 } };
```
