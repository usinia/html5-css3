# HTML5 & CSS3

모두의 HTML5 & CSS3

## 1. 웹 사이트 설계를 위한 HTML

### DAY 01. 웹을 구성하는 요소

#### 웹 사이트 레이아웃

브라우저의 너비에 따라 웹 사이트 공간의 크기와 배치의 변화로 쉽게 파악

- 정적 레이아웃 - 공간의 크기가 변하지 않는 고정 레아이웃
- 동적 레이아웃 - 브라우저 너비와 상관없이 화면에 콘텐츠가 꽉 채워지도록 제작하는 방식
- 적응형 레이아웃 - 브라우저 너비에 따라 레이아웃이 변경되는 방식
- 반응형 레아이웃 - 동적 레이아웃과 적응형 레아이웃을 결합한 방식

#### 크로스 브라우징

사용자가 어떤 버전의 브라우저로 접속할지 알 수 없으므로 다양한 브라우저와 버전에 대응할 수 있도록 제작하는 방식

#### 웹 표준

팀 저너스 리가 중심으로 1994년 10월에 설립된 W3C가 개발한 웹 기술 표준 가이드라인

구글 등 검색 사이트 노출, 장애/비장애인 접근성인 웹 접근성, 유지보수 및 관리에 용이하다.

### DAY 03. HTML과 레이아웃 (index.html)

#### 웹 사이트 공간을 정의하는 태그

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8" />
    <title>웹 프로그래밍 기초</title>
  </head>
  <body>
    <header>
      <h1><img src="logo.png" alt="이미지 설명" /></h1>
      <nav>
        <ul>
          <li><a href="#">메뉴 1</a></li>
        </ul>
      </nav>
    </header>
    <main role="main">
      <p>웹 사이트의 본문 내용 전체를 감쌀 때 사용</p>
      <p>IE 호환을 위해 role='main' 속성값을 사용한다.</p>
      <section>
        <h2>웹 사이트 영역 설정할 때 사용</h2>
        <p>h1~6이 반드시 포함되어야 한다.</p>
        <aside><p>페이지 주요 내용과 연관성 적은 내용</p></aside>
        <article>
          <h3>페이지와 연관성 큰 내용</h3>
          <p>h1~6이 만드시 포함되어야 한다.</p>
        </article>
      </section>
    </main>
    <footer>
      <p>회사 정보 입력할 때 사용</p>
    </footer>
  </body>
</html>
```

#### HTML의 Block 요소와 Inline 요소

세로로 아이템이 정렬되는 것이 Block 요소로 h1~6, p, header, section, main, aside, footer, div 태그가 있다.

가로로 아이템이 정렬되는 것이 Inline 요소로 span, a, input 태그가 있다.

css display 속성을 사용해 성격을 바꿀 수 있다.

## 2. 웹 디자인을 담당하는 CSS

### DAY 04. CSS 시작하기

#### CSS 구성요소와 연동 방법

- 인터널 방식 : HTML 문서 안에 style 태그를 사용하여 적용
- 인라인 방식 : HTML 태그 안에 style 속성을 사용하여 적용
- 익스터널 방식 : CSS 파일을 생성하여 HTML 문서와 연동

#### CSS 선택자

디자인을 적용할 HTML 영역으로 type, id, class로 구분된다.

### DAY 05. CSS 사용하기 (index01.html)

#### 부모 자식 간의 CSS 상속

HTML에서 태그가 태그를 포함하는 관계를 부모-자식 관게라고 한다. 부모 태그에 CSS 속성을 적용하면 자식 태그가 상속받는 속성이 존재한다.

#### CSS 속성의 우선순위, 케스케이딩

케스케이딩은 같은 영역에 디자인을 적용했을 때 어느 디자인이 우선해서 적용하는지를 나타낸다. 우선순위에 영향을 미치는 것은 다음과 같다.

- CSS 속성이 입력된 순서 - 나중에 적용된 CSS가 우선순위가 높다.
- 선택자를 구체적으로 입력했는지 여부
- id, class, type 선택자

인라인 방식 > id 선택자 > class 선택자 > type 선택자

### DAY 06. CSS 주요 속성 익히기 (index02.html)

img와 background-image의 차이

정보성 이미지면 img를 사용하고 장식용 이미지는 background-image를 사용한다. img 태그를 사용하면 원본 이미지를 사용하기 때문에 width, height을 변경해도 이미지가 잘리지 않지만, background-image는 공간이 남거나 이미지가 잘린다.

## 3. 웹 사이트 제작 한 걸음 더

### DAY 07. 레이아웃에 영향을 미치는 요소 1

#### 박스 모델의 4가지 요소

박스 모델에는 박스의 크기와 간격을 정의하는 margin, border, padding, content 속성이 있다.

- margin - border 속성을 기준으로 바깥쪽 영역을 의미. 좌표를 설정할 때 사용.
- border - 공간의 테두리. 선의 종류(실선, 점선)와 선의 굵기, 선의 색을 속성으로 지정
- padding - border 속성과 content 속성의 간격을 의미. 좌표를 설정할 때 사용.
- content - 태그에 포함되어 있는 내용 영역을 의미

#### 마진 병합

margin-top과 margin-bottom 속성이 제대로 적용되지 않을 때는 마진 병합(collapsing margins) 때문이다. 마진 병합이란 인접한 공간에 두 속성을 적용할 경우 두 속성 중 큰 속성값이 작은 속성값을 병합하는 현상을 말한다.

### DAY 08. 레이아웃에 영향을 미치는 요소 2

#### display 속성

- inline - 줄바꿈이 일어나지 않음. width, height, margin이 적용되지 않음.
- block - 줄바꿈이 일어남. width, height, margin이 적용됨
- inline-block - 줄바꿈은 일어나지 않지만 width, height, margin이 적용됨.

#### position 속성 - 2차원과 3차원이 존재

##### 2차원 static

static 속성값은 부모-자식 간에 발생하는 마진 병합 현상이 일어나고, top, left, right, bottom 속성이 적용되지 않고, 자식의 높이가 부모에 영향을 준다. position의 기본값이다.

```css
#position_static_parent {
  width: 500px;
  /* static 속성값은 부모의 높이에 영향을 줄 수 있다. */
  /* height: 500px; */
  background-color: yellow;
}
#position_static_child {
  position: static;
  /* static 속성과 margin-top 속성을 함께 사용하면 마진 병합 현상이 일어난다.
  => 부모가 자식과 함께 margin-top 적용됨 */
  margin-top: 100px;
  /* static과 top 속성은 함께 사용할 수 없다. */
  top: 100px;
}
```

##### 3차원 fixed

fixed 속성값은 부모-자식 간에 발생하는 마진 병합 현상이 일어나지 않고, top, right, bottom, left 속성이 적용되고, 부모가 자식 높이에 영향을 받지 않는다.

fixe에서는 margin-top은 요소가 최초로 생성된 지점을 기준으로 하고, top은 웹 브라우저를 기준으로 하기 때문에 위치가 다르다.

##### 2차원과 3차원 relative

relative 속성값은 2차원과 3차원의 특징을 모두 갖는다. 부모-자식 간에 발생하는 마진 병합 현상이 일어나고, top, right, bottom, left 속성이 적용되며, 부모가 자식 높이에 영향을 받는다. margin-top 속성을 사용하면 static처럼 마진 병합 현상이 일어난다.

##### 3차원 absolute

absolute 속성값은 부모-자식 간에 마진 병합 현상이 일어나지 않고, top, right, bottom, left 속성이 적용되며 부모의 position에 따라 좌표 기준점이 달라진다. 부모가 자식 높이에 영향을 받지 않는다.

부모의 position이 relative이면 margin-top과 top의 기준점이 부모에서 시작하는 처음 위치로 동일하며, static일 경우 top은 웹 브라우저를 기준으로 한다.

### DAY 09. 레이아웃에 영향을 미치는 요소 3

#### z-index

z축은 레이어 높낮이에 영향을 준다. z-index로 사용하며 position이 fixed, relative, absolute 속성값인 3차원 요소와 함께 사용할 수 있다. 정수로 표현하며 숫자가 높을수록 상위 레이어로 표현된다.

#### float

선택된 태그를 띄워서 부모의 공간을 기준으로 왼쪽 끝이나 오른쪽 끝에 배치할 때 사용한다. `float: left;` 나 `float: right;`로 사용한다.

2차원 > 3차원 형제일 경우는 두 요소 모두 출력되지만, 3차원 > 2차원 형제일 경우 요소가 겹쳐서 첫 번째 요소만 노출된다. float도 마찬가지다.

#### float과 clear

clear 속성은 float 속성의 기능을 제어하는 데 사용한다. 속성값은 left, right, both 등이 있다. 즉 left를 삭제, right를 삭제, 둘 다 삭제한다는 의미이며 일반적으로 `clear: both;`를 사용한다.

### DAY 10. CSS3에 등장한 신조어

#### transform

태그의 각도를 조정하고 크기를 변경하며 위치를 옮길 때 사용하는 속성으로 속성값으로 rotate, scale, skew, translate 등이 있다.

`transform: rotate(45deg)`로 사용하며 양수는 시계방향, 음수는 반시계방향으로 회전한다.

`transform: scale(1.5, 0.5)`로 사용하며 너비, 높이의 비율이 변경된다. 1을 기준으로 크면 확대, 작으면 축소한다.

`transform: skew(10deg, 20deg)`로 사용하며, 각도를 입체적으로 조정할 때 사용한다. 양수면 오른쪽/아래, 음수면 왼쪽/위쪽으로 공간이 왜곡된다.

`transform: translate(100px, 200px)`로 사용하며, 요소의 위치를 이동시킬 때 사용한다.

#### transition

마우스 포인터를 올리는 등 특정 조건에 따라 상태가 변하는 것을 뜻한다.

```css
#transition {
  width: 300px;
  height: 300px;
  background-color: yellow;

  /* 변화 과정을 보여 주고자 하는 속성은 width이다. */
  transition-property: width;

  /* width 300px에서 width 600px로 바뀌는 데 걸리는 시간은 3초다. */
  transition-duration: 3s;

  /* 초반은 느리게, 중반은 빠르게, 종반은 느리게 변화가 진행된다. */
  transition-timing-function: ease;

  /* 마우스 포인터를 올렸을 때 1초 후에 변화가 시작된다. */
  transition-delay: 1s;

  /* 한 줄로 */
  /* transition: width 3s ease 1s; */
}

/* #transition에 마우스 포인터를 올렸을 때 width 속성값이 600px로 변한다. */
#transition:hover {
  width: 600px;
}
```

#### animation

GIF나 플래시처럼 웹 사이트에 다양한 애니메이션 효과를 적용할 때 사용한다. @keyframes 가 짝으로 존재한다.

```css
#animation {
  width: 300px;
  height: 300px;
  background-color: yellow;
  /* 애니메이션 이름 */
  animation-name: changeWidth;
  /* 애니메이션이 from~to로 동작하는 데 걸리는 시간 */
  animation-duration: 3s;
  /* 애니메이션 재생 횟수. from-to가 1회로 왕복은 2회이다. */
  animation-iteration-count: 6;
  /* 속도의 가속과 감속 설정 */
  animation-timing-function: ease;
  /* 애니메이션 진행 방향. normal: from~to, reverse: to~from, alternate: from~to&to~from, alternate-reverse: to~from&form~to */
  animation-direction: alternate;
  /* 애니메이션 동작 시간 지연, 기본값 0s */
  animation-delay: 2s;

  /* 한 줄로 */
  animation: changeWidth 3s 6 ease alternate 2s;
}

/* @keyframes 옆에는 animation-name 속성의 속성값을 입력한다. */
@keyframes changeWidth {
  from {
    width: 300px;
  }
  to {
    width: 600px;
  }
  /* 혹은 */
  0% {
    width: 300px;
  }
  50% {
    background-color: red;
  }
  100% {
    width: 600px;
  }
}
```

#### 신조어와 브라우저 호환성 접두사

신조어는 이전 버전의 브라우저에서는 지원하지 않는다. 호환성을 위해 각 브라우저는 접두사를 붙인 속성을 지원하는데, -ms-, -webkit-, -moz-, -o- 등이 있다. 모든 신조어를 지원하는 것은 아니다. 접두사를 먼저, 이후에 신조어를 작성하는데 이는 css의 우선순위가 나중에 작성한 속성에 있기 때문이다.

### DAY 11. 메뉴 버튼 만들기

index03.html, style03.css

## 4. 만들어보자! 키즈가오 웹 사이트
