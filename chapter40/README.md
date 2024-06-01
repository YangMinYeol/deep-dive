# 이벤트

- 이벤트가 발생했을 때 호출될 함수를 `이벤트 핸들러`라 한다.
- 이벤트가 발생했을 때 브라우저에게 이벤트 핸들러의 호출을 위임하는 것을 `이벤트 핸들러 등록`이라 한다.

## 이벤트 드리븐 프로그래밍

- 이벤트와 그에 대응하는 함수를 통해 사용자와 애플리케이션은 상호작용을 할 수 있다. 이와 같이 프로그램의 흐름을 이벤트 중심으로 제어하는 프로그래밍 방식을 `이벤트 드리븐 프로그래밍`이라 한다.

##### 마우스 이벤트

- `click` - 마우스 버튼을 클릭했을 때
- `dblclick` - 마우스 버튼을 더블 클릭했을 때
- `mousedown` - 마우스 버튼을 눌렀을 때
- `mouseup` - 누르고 있던 마우스 버튼을 놓았을 때
- `mousemove` - 마우스 커서를 움직였을 때
- `mouseenter` - 마우스 커서를 HTML 요소 안으로 이동했을 때(버블링 되지 않는다)
- `mouseover` - 마우스 커서를 HTML 요소 안으로 이동했을 때(버블링된다)
- `mouseleave` - 마우스 커서를 HTML 요소 밖으로 이동했을 때(버블링 되지 않는다)
- `mouseout` - 마우스 커서를 HTML 요소 밖으로 이동했을 때(버블링된다)

##### 키보드 이벤트

- `keydown` - 모든 키를 눌렀을 때
- `keypress` - 문자 키를 눌렀을 때 연속적으로 발생한다
- `keyup` - 누르고 있던 키를 놓았을 때

##### 포커스 이벤트

- `focus` - HTML 요소가 포커스를 받았을 때(버블링되지 않는다)
- `blur` - HTML 요소가 포커스를 잃었을 때(버블링되지 않는다)
- `focusin` - HTML 요소가 포커스를 받았을 때(버블링된다)
- `focusout` - HTML 요소가 포커스를 잃었을 때(버블링된다)
- `focusin`, `focusout` 이벤트 핸들러는 addEventListener 메서드 방식을 사용해 등록해야 한다.

##### 폼 이벤트

- `submit` - form 요소 내의 input, select 입력 필드에서 엔터키를 눌렀을 때 / form 요소 내의 submit 버튼을 클릭했을 때
- `reset` - form 요소 내의 reset 버튼을 클릭했을 때(최근에는 사용 안 함)

##### 값 변경 이벤트

- `input` - input, select, textarea 요소의 값이 입력되었을 때
- `chage` - input, select, textarea 요소의 값이 변경되었을 때
- `readystatechage` - HTML 문서의 로드와 파싱 상태를 나타내는 document.readyState 프로퍼티 값이 변경될 때

##### DOM 뮤테이션 이벤트

- `DOMContentLoaded` - HTML 문서의 로드와 파싱이 완료되어 DOM 생성이 완료되었을 때

##### 뷰 이벤트

- `resize` - 브라우저 윈도우의 크기를 리사이즈할 때 연속적으로 발생한다.
- `scroll` - 웹페이지 또는 HTML 요소를 스크롤할 때 연속적으로 발생한다.

##### 리소스 이벤트

- `load` - DOMContentLoaded 이벤트가 발생한 이후, 모든 리소스의 로딩이 완료되었을때
- `unload` - 리소스가 언로드될 때
- `abort` - 리소스 로딩이 중단되었을 때
- `error` - 리소스 로딩이 실패했을때

## 이벤트 핸들러 등록

##### 이벤트 핸들러 어트리뷰트 방식

- onclick과 같이 on 접두사와 이벤트의 종류를 나타내는 이벤트 타입으로 이루어져 있다.
- 이벤트 핸들러 어트리뷰트 값으로 함수 호출문 등의 문을 할당하면 이벤트 핸들러가 등록된다.
- 이벤트 핸들러 어트리뷰트 값은 사실 암묵적으로 생성될 이벤트 핸들러의 함수 몸체를 의미한다.
- 이벤트 핸들러 어트리뷰트 방식은 오래된 코드에서 간혹 이 방식을 사용한 것이 있기 때문에 알아둘 필요는 있지만 더는 사용하지 않는 것이 좋다.
  > HTML과 자바스크립트는 관심사가 다르므로 혼재하는 것보다 분리하는 것이 좋다.

##### 이벤트 핸들러 프로퍼티 방식

- 이벤트 핸들러 어트리뷰트와 마찬가지로 onclick과 같이 on 접두사와 이벤트의 종류를 나타내는 이벤트 타입으로 이루어져 있다.
- 이벤트 핸들러를 등록하기 위해서는 이벤트를 발생시킬 객체인 `이벤트 타깃`과 이벤트의 종류를 나타내는 문자열인 `이벤트 타입` 그리고 `이벤트 핸들러`를 지정할 필요가 있다.
- 이벤트 핸들러 프로퍼티에 하나의 이벤트 핸들러만 바인딩할 수 있다는 단점이 있다.

##### addEventListener 메서드 방식

- 하나 이상의 이벤트 핸들러를 등록할 수 있다. 이때 이벤트 핸들러는 등록된 순서대로 호출된다.
  > addEventListener 메서드를 통해 참조가 동일한 이벤트 핸들러를 중복 등록하면 하나의 이벤트 핸들러만 등록된다.

## 이벤트 핸들러 제거

- `removeEventListener` 메서드를 사용한다.
- 무명 함수를 이벤트 핸들러로 등록한 경우 제거할 수 없다.
- 기명 이벤트 핸들러 내부에서 `removeEventListener` 메서드를 호출하여 이벤투 핸들러를 제거하는 것은 가능하다.
- 이벤트 핸들러 프로퍼티 방식으로 등록한 이벤트 핸들러는 `removeEventListener` 메서드로 제거할 수 없다.
  > 제거 방법은 이벤트 핸들러 프로퍼티에 null을 할당한다.

## 이벤트 객체

- 이벤트가 발생하면 이벤트에 관련한 다양한 정보를 담고 있는 이벤트 객체가 동적으로 생성된다. 생성된 이벤트 객체는 이벤트 핸들러의 첫 번째 인수로 전달된다.
- 이벤트 핸들러 어트리뷰트 방식의 경우 이벤트 객체를 전달받으려면 이벤트 핸들러의 첫 번째 매개변수 이름이 반드시 event이어야 한다.

##### 이벤트 객체의 공통 프로퍼티

- Event 인터페이스의 이벤트 관련 프로퍼티는 모든 이벤트 객체가 상속받는 공통 프로퍼티다.
- `type` - 이벤트 타입
- `target` - 이벤트를 발생시킨 DOM 요소
- `currentTarget` - 이벤트 핸들러가 바인딩된 DOM 요소
- `eventPhase` - 이벤트 전파 단계
- `bubbles` - 이벤트를 버블링으로 전파하는지 여부
- `cancelable` - preventDefault 메서드를 호출하여 이벤트의 기본 동작을 취소할 수 있는지 여부
- `defaultPrevented` - preventDefault 메서드를 호출하여 이벤트를 취소했는지 여부
- `isTrusted` - 사용자의 행위에 의해 발생한 이벤트인지 여부
- `timeStamp` - 이벤트가 발생한 시각

## 이벤트 전파

- 생성된 이벤트 객체는 이벤트를 발생시킨 DOM 요소인 이벤트 타깃을 중심으로 DOM 트리를 통해 전파된다.
  1. `캡처링` - 이벤트가 상위 요소에서 하위 요소 방향으로 전파
  2. `타깃` - 이벤트가 이벤트 타깃에 전달
  3. `버블링` - 이벤트가 하위 요소에서 상위 요소 방향으로 전파

## 이벤트 위임

- 이벤트 위임은 여러개의 하위 DOM 요소에 이벤트 핸들러를 등록할 필요가 없다.
- 이벤트 위임을 통해 하위 DOM 요소에서 발생한 이벤트를 처리할 때 주의할 점은 상위 요소에 이벤트 핸들러를 등록하기 때문에 이벤트 타깃, 즉 이벤트를 실제로 발생시킨 DOM 요소가 개발자가 기대한 DOM 요소가 아닐 수도 있다는 것이다.

## DOM 요소의 기본 동작 조작

##### DOM 요소의 기본 동작 중단

- `preventDefault` 메서드는 DOM 요소의 기본 동작을 중단시킨다.

##### 이벤트 전파 방지

- `stopPropagation` 메서드는 이벤트 전파를 중지시킨다.

## 이벤트 핸들러 내부의 this

##### 이벤트 핸들러 어트리뷰트 방식

- 이벤트 핸들러를 호출할 때 인수로 전달한 this는 이벤트를 바인딩한 DOM 요소를 가리킨다.

##### 이벤트 핸들러 프로퍼티 방식과 addEventListener 메서드 방식

- 둘 다 이벤트 핸들러 내부의 this는 이벤트를 바인딩한 DOM 요소를 가리킨다. 즉 this는 이벤트 객체의 currentTarget 프로퍼티와 같다.
- `화살표 함수`로 정의한 이벤트 핸들러 내부의 this는 상위 스코프 this를 가리킨다. 화살표 함수는 함수 자체의 this 바인딩을 갖지 않는다.

## 이벤트 핸들러에 인수 전달

- 이벤트 핸들러 내부에서 함수를 호출하면서 임수를 전달할 수 있다.
- 이벤트 핸들러를 반환하는 함수를 호출하면서 인수를 전달 할 수 있다.

## 커스텀 이벤트

- 커스텀 이벤트 객체는 bubbles와 cancelable 프로퍼티의 값을 true로 설정하려면 이벤트 생성자 함수의 두 번째 인수로 bubbles 또는 cancelable 프로퍼티를 갖는 객체를 전달한다.

##### 커스텀 이벤트 디스패치

- 생성된 커스텀 이벤트는 dispatchEvent 메서드로 디스패치(이벤트를 발생시키는 행위)할 수 있다.