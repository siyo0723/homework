# 20240503 과제 코드설명

## HTML

> - <main class="main">: 페이지의 주요 콘텐츠를 감싸는 <main> 요소입니다.
> - .wrap1, .wrap2는 아바타 이미지를 포함하는 두 개의 컨테이너 입니다.
> - .faceImg는 아바타 이미지와 온라인/오프라인 상태를 나타내는 요소를 포함합니다.
> 이렇게 하여 각 아바타 이미지와 해당 상태를 나타내는 요소들이 표시되는 웹 페이지가 완성됩니다.

## CSS

> ### float을 사용한 레이아웃
> - .main 클래스에 부모 요소의 자식 요소들을 자식 요소로 포함시키도록 display: flow-root;속성을 적용합니다.
> - .wrap1과 .wrap2 클래스에 아바타 이미지 영역 간의 아래쪽 여백 추가, overflow: hidden;를 사용해 부모 요소의 높이는 자식 요소의 내용에 따라 자동으로 조절되도록 합니다.
> - .faceImg에서 float: left;로 요소를 왼쪽으로 정렬되도록 하고, 아바타 이미지 영역 간의 오른쪽 여백 추가 및 position: relative;로 요소의 위치를 상대적으로 지정하여 내부 요소들에 대한 위치 조정을 가능하게 합니다.

> ### flex를 사용한 레이아웃
> - @supports (display: flex):사용해 브라우저가 Flexbox를 지원하는지 확인하는 CSS 조건문을 활용합니다.
> - .main 클래스는 display: flex;를 사용해 flexbox 컨테이너로 만든 후, flex-flow: column nowrap;을 통해 아이템을 수직으로 정렬하고(column) 여러 줄에 걸쳐 표시하지 않도록 합니다(nowrap).
> - .wrap1에 order: 2;를 사용해 .wrap1 요소의 표시 순서를 변경하여 .wrap2 요소 뒤로 이동시킵니다.
> - .faceImg는 아이템들의 사이에 오른쪽 여백을 추가되도록 하고, position: relative;로  요소의 위치를 상대적으로 지정하여 내부 요소들에 대한 위치 조정을 가능하도록 합니다.

> ### 공통으로 사용된 css
> - * { margin: 0; }: 모든 요소의 마진을 초기화하여 브라우저의 기본 스타일을 제거하도록 합니다.
> - img { width: 64px; height: 64px; border-radius: 50%; }: 이미지 요소에 고정된 너비와 높이, 원형 모양의 테두리를 적용하여 프로필 이미지처럼 보이도록 스타일을 지정합니다.
> - .activity { ... }: 활동 상태를 나타내는 요소의 스타일을 지정합니다.
> - .activity를 nth-child를 활용하여 활동 상태의 색상을 다르게 지정합니다. (class명 지졍 변경보다 가상 요소의 순서를 바꿔 활용해보고 싶어 사용했습니다.)