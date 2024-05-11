# 20240510 과제 코드설명

## HTML

> - <div class="container" role="group">: 페이지의 전체 콘텐츠를 감싸는 컨테이너입니다. role 속성을 사용하여 그룹 역할을 부여했습니다.
> - <form action="/" class="login-form">: 회원 로그인을 위한 폼 요소입니다. action 속성을 통해 제출할 URL을 지정했습니다.
> - <fieldset>, <legend class="">를 사용해 폼 그룹을 위해 사용하였습니다.
> - <input type="email" id="userEmail" required placeholder=" 아이디(이메일)" name="userEmail" />: 이메일 형식의 아이디 입력 필드입니다. required 속성을 사용하여 필수 입력 필드임을 지정했습니다. (비밀번호 입력 서식 동일)
> - <form action="/" class="login-status-form">: 로그인 상태 및 보안 옵션을 입력하는 폼 요소입니다.
> - <div class="keep-login">: 로그인 상태 유지를 나타내는 컨테이너입니다.
> - <label for="login-toggle" aria-label="로그인 상태 토글">: 체크박스 입력 요소에 대한 레이블입니다. aria-label 속성을 통해 스크린 리더 사용자에게 명시적인 설명을 제공합니다.
> - class="status-btn-uncheck" / class="status-btn-check" 이미지를 활용해 비활성화, 활성화 상태를 시각적으로 나타냈습니다.
> - <div class="ip-security">: IP 보안 설정을 나타내는 컨테이너입니다
> - <a href="/homework/naver/ip_security.html" target="_blank">IP 보안</a>: IP 보안에 대한 정보를 제공하는 링크입니다. 새 탭에서 열립니다.
> - <label for="ip-security-toggle" aria-label="IP 보안 토글">: 체크박스 입력 요소에 대한 레이블입니다. aria-label 속성을 통해 스크린 리더 사용자에게 명시적인 설명을 제공합니다.
> - span 태그를 사용해  체크되지 않은 상태의 텍스트와 체크된 상태의 텍스트를 시각적인 상태 변화를 위해 사용하였습니다.

## CSS

> /* reset 초기 셋팅 */을 통해 기본 스타일을 초기화 진행하였습니다.
<details>
<summary>미디어 쿼리를 사용한 SVG 및 PNG 이미지 처리.</summary>

<svg를 지원하는 경우>
- @media (min-width: 0): 미디어 쿼리를 사용하여 모든 화면 크기에서 적용됩니다. 이는 사실상 모든 환경에서 적용되는 것을 의미합니다.
<svg를 지원하지 않는 경우>
@media not all and (min-resolution: .001dpcm): 미디어 쿼리를 사용하여 해상도가 매우 낮은 경우를 제외한 모든 환경에서 적용됩니다.

이렇게 함으로써 브라우저가 SVG 이미지를 지원하는 경우에는 SVG 이미지를, 그렇지 않은 경우에는 PNG 이미지를 표시하게 됩니다.
- 
</details>

> - /* 공통 스타일 및 모바일 스타일 */에서 모바일 기준으로 우선적으로 기본 디자인 구성을 진행했습니다.
> - /* 로그인 상태 유지 및 IP 보안 */의 경우에는   display: flex;와  align-items: center;을 사용해 정렬을 한 후에,
> - 로그인 상태 유지인 .login-status-form .keep-login을 오른쪽으로 정렬, ip보안인 .login-status-form .ip-security 을 안보이게 display: none;처리 하였습니다.
> - 마우스 및 키보드 작동 시 체크버튼 svg와 ip의 on/off의 경우 사용한 checkbox속성을 동작 시 활성화/ 비활성화 되도록 (.클래스명:checked + label .클래스명)을 사용해 처리하였습니다. (해당 기능 주석 설명 기재)
> - /* 데스크탑 사이즈 */을 통해 모바일과 다른 구성을 지정하였습니다.
> - 모바일 사이즈에서 정렬 위치가 달랐던 로그인 상태 유지인  .login-status-form .keep-login을 왼쪽으로 정렬, ip보안인  .login-status-form .ip-security을 다시 보이게끔 block 처리 및 오른쪽 정렬로 배치 구성을 변경하였습니다.

## 해결하지 못한 코드

> - 로그인 상태 유지 및 ip보안을 조작하는 checkbox 버튼을 사용하였는데 해당 요소를 none처리로 가릴 시 마우스 클릭으로는 활성화 할 수 있지만 키보드 조작으로는 불가능한 것을 확인했습니다.
> - 그 후 checkbox가 아닌 button 태그와 radio요소를 활용해 다시 코드를 시도해보았으나 해당 코드로 작성할지 키보드 동작은 가능하지만 마우스로는 동작하지 못하도록 됐습니다.
> - 하지만 고민 후에 반복되게 같은 지점을 클릭하는 요소이기에 checkbox로 다시 수정했으나 none처리 방식이 아닌 다르게 없애는 방식을 고민하다가 해당 조건 하나를 미처 완성해내지 못했습니다.
> - 1개의 조건을 완성하지 못해 미완성이 되었지만 고민을 하면서 많이 찾아보고 기능 요소들을 비교해보는 시간을 가지게 되었고 폼 요소를 더욱 이해하는 과제가 되었던 것 같습니다.
> - 완성되지 못한 부분은 선생님께 배워 조금 더 활용해 다시 완성해보도록 하곘습니다 감사합니다!