> 개발자도구를 많이 사용하셨다면 주로 어떤 용도로 사용했나요?

- Elements 탭
  Elements 편집기를 사용하여 코드 편집기에서 HTML, CSS 코드를 변경하지 않고 페이지에서 직접 변경해보면서 레이아웃과 디자인을 테스트 할 때 사용하였습니다. 또한 클론코딩을 할때에 인스펙션 기능을 사용하여 HTML구조와 CSS를 확인하였습니다.
- Styles 탭
  특정 HTML 요소의 스타일을 추가, 테스트하는데 주로 사용했으며, CSS 속성의 이름을 검색해 특정 속성값을 찾는데도 사용했습니다.
- console 탭
  경고, 에러 등의 메시지를 확인하여 디버깅을 하는데 주로 사용했습니다. 또한 원하는 기능이 제대로 실행 되는지 log로 출력하여 확인할때 사용했습니다. 기존에 작성한 자바스크립트 코드를 수정하지 않고도 DOM을 조작할 수 있다.
- Application 탭
  Local Storage, Session Storage, Cookie에 저장된 데이터를 확인하는 데 사용한다.
- Network 탭
  API 데이터가 잘 넘어왔는지 확인할때 사용하였습니다.

> 웹팩과 바벨의 역할에 대해서 설명하세요.

- **웹팩**은 **자바스크립트 어플리케이션을 위한 정적 모듈 번들러입니다**. 모듈은 우리가 작성한 자바스크립트 소스코드와 우리가 사용한 라이브러리들입니다. 번들러는 의존성 있는 모듈을 하나의 파일로 통합시켜주는 도구입니다.
  웹팩의 역할으로는
  웹페이지에서 기능단위의 코드를 모듈화 하여 이해하기 쉽고 가독성과 유지보수성이 좋은 효율적인 개발을 할수 있도록 합니다. 그리고 배포시에는 자바스크립트 파일을 한번에 다운로드 할 수 있도록 하나로 병합하는데(합쳐주는데) 이것으로 네트워크 병목현상을 방지하는 역할을 합니다.
- 브라우저들은 각기 다른 엔진을 사용합니다. 각기 다른 엔진들은 각기 다른 버전을 지원하고 자신이 지원하는 버전보다 최신버전의 자바스크립트를 사용하면 읽어들이지 못해 오류가 발생합니다. 따라서 최신버전의 코드들을 각기다른 버전을 지원하는 엔진이 읽을수 있는 legacy문법으로 변환하여 사용이 가능하게 합니다. 바벨은 트랜스파일러로 하나의 언어로 작성된 코드를 다른언어로 바꾸는 컴파일러와는 다르게 같은언어지만 다른 문법으로 바꾸어주는 역할을 합니다.

---

### 정의-네트워크 병목 현상이란 무엇입니까?

네트워크 병목 현상은 컴퓨터 또는 네트워크 리소스에 의해 데이터 흐름이 제한되는 불연속 조건을 나타냅니다. 데이터 흐름은 다양한 시스템 리소스의 대역폭에 따라 제어됩니다. 네트워크에서 작동하는 시스템이 기존 네트워크 용량에서 지원하는 것보다 많은 양의 데이터를 전달하는 경우 네트워크 병목 현상이 발생합니다.

---

> event.preventDefault() 의 역할이 무엇인지 설명하세요.

특정 이벤트가 일어나면, 해당 이벤트에는 디폴트 액션들이 있어서 자동으로 액션이 일어나게 됩니다. 예를들어 form 태그 같은 경우 onSubmit 이벤트에 새로고침이 되는 디폴트 액션이 있습니다. 이때 preventDefault를 사용하면 해당 이벤트의 디폴트 액션을 취소시키는 역할을 합니다. checkbox의 경우에는 checkbox가 토글링 되는데 preventDefault를 사용하면 이 역시 토글링을 취소시키게 됩니다.
