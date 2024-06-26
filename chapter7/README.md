# 연산자

- `연산자`는 하나 이상의 표현식을 대상으로 산술, 할당, 비교, 논리, 타입, 지수 연산 등을 수행해 하나의 값을 만든다.
- 연산의 대상을 `피연산자`라 한다.

## 산술 연산자

- `피연산자`를 대상으로 수학적 계산을 수행해 새로운 숫자 값을 만든다.
- 산술 연산이 불가능한 경우, NaN을 반환한다.

## 비교 연산자

- 동등 비교(==) 연산자는 좌항과 우항의 피연산자를 비교할 때 암묵적 타입변환을 통해 타입을 일치시킨 후 같은 값인지 비교한다.
- 일치 비교(===) 연산자는 좌항과 우항의 피연산자가 타입도 같고 값도 같은 경우에 한하여 true를 반환한다.
  > NaN은 자신과 일치하지 않는 유일한 값이다. 따라서 숫자가 NaN인지 조사하려면 빌트인 함수 Number.isNaN을 사용한다.

## 삼항 조건 연산자

- 조건식 ? 조건식이 true일 때 반환할 값 : 조건식이 false일 때 반환할 값
- 삼항 조건 연산자 표현식은 값으로 평가할 수 있는 표현식인 문이다.

## 지수 연산자

- 좌항의 피연산자 밑으로, 우항의 피연산자를 지수로 거듬제곱하여 숫자 값을 반환한다.
- 음수를 거듭제곱의 밑으로 사용해 계산하려면 다음과 같이 괄호로 묶어야 한다.
  > (-5) \*\* 2; // 25
