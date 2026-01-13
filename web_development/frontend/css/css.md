# CSS (Cascading Style Sheets)

- Describes how HTML elements are to be displayed on screen.

## 기본 구성요소

- Selector: ex. h1
- Property: ex. background-color
- Value: ex. blue

## 3 ways to insert CSS

1. External
  - ex. <link ref='stylesheet' href='(...)'>
2. Internal
  - ex. <style></style>
3. Inline
  - ex. <p style="color: red;">Hello World</p>

- Developer Tool을 자주 사용하자!

## Combinators

- Selectors 사이에 combinator를 넣어서 하나의 selector가 하나 이상의 simple selector를 가지게 할 수 있음.

### Descendant combinator

- Descendant combinator => ex. div p {} 후손 (직계, 손자, 증손자 p 전부)
- matches all elements that are descendants of a specific element (즉, div 내에 있는 모든 p 태그만)

### Child combinator

- Child combinator => ex. div > p {} 직계 자식 (직계 p만)
- selects all elements that are the children of a specific element (즉, div내에 있는 직계 p태그만 선택함. 만약 div내의 section 태그 내에 p태그가 있다면, 이 태그는 선택되지 않음!)

### Next sibiling combinator

- Next sibiling combinator => ex. div + p {} 인접 형제 (같은 부모, 바로 뒤)
- used to select an element that is directly after another specific element (즉, 같은 부모를 가진 div 바로 뒤에 오는 p태그를 선택. 이때 순서상 div 태그 이후에 나와야만 적용이 됨. 즉, 같은 depth를 가지는 (parent element가 같은) & div 태그 바로 뒤에 선언된 하나의 p태그를 선택)

### Subsequent sibling combinator

- Subsequent sibling combinator => ex. div ~ p {} 일반 형제 (같은 부모, 순서 뒤)
- selects all elements that are next siblings of a specific element (즉, 같은 부모를 가진 div 뒤에 나오는 모든 p태그를 선택. 이때 순서상 div 태그 이후에 나와야만 적용이 됨. 즉, 같은 depth를 가지는 (parent element가 같은) & div 태그 이후에 선언된 모든 p태그를 선택)

## Attribute selector
![img.png](img%2Fimg.png)

## 자주 사용되는 properties

### size

- max-width / min-width / max-height / min-height: 100px;
- max: 최대 width/height 제한 (width/height가 이보다 크면 줄어듦)
- min: 최소 width/height 제한 (width/height가 이보다 작으면 커짐)
- width/height보다 우선적용!!!

### outline

- outline-style / outline-width / outline-color / outline: width style color
- border처럼 content의 boundary가 아닌, margin의 boundary outline을 꾸밂

### opacity

- opacity: 0.2;
- 투명도

### transition

- transition: property second; => ex. transition: background-color 0.15s;
- 해당 element에 대해, property가 변경되면 특정 초만큼 transition

### Overflow

- Overflow: visible / hidden / scroll / auto;
- Controls what happens to content that is too big to fit into an area (특정 area에 fit하기에 너무 큰 content를 컨트롤)
- visible (default): the overflow is not clipped. The content renders outside the element's box
- hidden: the overflow is clipped, and the rest of the content will be invisible
- scroll: the overflow is clipped, and a scrollbar is added to see the rest of the content
- auto: similar to scroll, but it adds scrollbars only when necessary
- Overflow-x / Overflow-y

## Text

- Text:
- text-align: left / center / right / justify
- text의 horizontal alignment를 지정 (text-align: justify; 는 지정된 width 내에서 text를 stretch해 배치함)
- text-decoration-line: overline / line-through / underline / overline underline (혼합)
- text-decoration-color
- text-decoration-line은, 해당 text에 어떻게 line을 추가할지를 결정하고, text-decoration-color는, 해당 line의 색상을 결정
- Shortcut: text-decoration: style color;
-  text-transform: uppercase / lowercase / capitalize
- text를 대문자, 소문자, 맨 앞글자만 대문자로 임의 지정가능
- letter-spacing: 1px;
- text의 글자간 간격을 조정
- word-spacing: 10px;
- text의 단어간 간격을 조정
- line-height: 10px;
- text의 line간 간격을 조정 (상하)
-  text-shadow: 2px 2px 5px red;
- text의 그림자를 조절. Value는 순서대로 horizontal shadow, vertical shadow, blur, color를 나타냄.
- white-space: normal(default) / nowrap / pre / pre-wrap / pre-line / break-spaces
- 공백 처리 + 줄바꿈 처리를 한번에 제어하는 속성
- nowrap: [버튼/메뉴 한줄 유지에 사용] 한줄로만 표시. 영역을 넘어가면 스크롤바 생김
- pre: [코드 블록이나 포맷 유지] HTML에서 작성한 공백 및 줄바꿈 그대로 표시 (마치 <pre> 태그처럼)
- pre-wrap: [코드 블록이나 포맷 유지] 공백과 줄바꿈은 그대로 유지하면서 너무 길면 자동 줄바꿈
- pre-line: [문단 줄바꿈만 유지] 줄바꿈 문자는 인식하지만, 여러 공백은 한 칸으로 축소.

## Link

- Link:
- a:link
- a normal, unvisited link
- a:visited
- a link the user has visited
- a:hover
- a link when the user mouses over it
- a:active
- a link the moment it is clicked

## pointer-events

- pointer-events:

## !important

- [!important]
- "이 속성을 다른 어떤 rule보다 우선 적용하라" 라는 우선순위 최상위 선언

- p {
- color: red !important; /* 무조건 빨간색 적용*/
- }

## CSS 우선순위

- CSS는 다음의 순서로 우선순위가 결정됨:
- Inline style
- ID selector
- class, property selector
- tag selector
- Default style of the browser
- => 하지만 !important를 쓰면 이 순서를 무시하고 무조건 덮어씀!
- 자주 쓰면 유지보수가 힘들어지므로, production code에서는 지양

## initial vs. inherit vs. unset

- [initial vs. inherit vs. unset]
- 우선, inherit이 가능한 property vs. 불가능한 property를 알고 있어야 함.
- 상속 가능: ex. color, font-family
- 상속 불가능: ex. margin, padding, border

- initial: 속성을 브라우저 기본값으로 되돌림
- inherit: 부모 값 그대로 상속
- parent element가 property를 가지고있지 않다면 의미가 없음!
- unset: 상속 가능한 속성은 inherit하고, 아니면 initial함
- "그 속성이 원래 상속되면 inherit, 아니면 initial로 초기화"하는 자동 복원버튼같은 역할

## Semantic element

- [Semantic element]
- 브라우저와 개발자가 그 의미를 명확하게 설명하는 요소로, element의 name에 의미를 충분히 담은 요소 => tag에 의미를 담아 콘텐츠 영역을 논리적으로 구분하기 위해!

- <article>: 블로그 포스트, 신문기사 등
- <aside>
- <details>
- <figcaption>
- <footer>
- <header>
- <main>
- <mark>
- <nav> : 목차, 색인, 메뉴에 사용
- <section> : 하나의 구역을 구분하는데 사용(<div>대신 사용)
- <summary>
- <time>

## CSS Display Properties

- There are 3 CSS Display Properties:
- => Allow to control how the element is displayed

- display: inline;
- Appear within a line of text (e.g., <b>, <i>)
- display: inline-block;
- only takes up as much space as needed. => The element itself is formatted as an inline element, but you can apply height and width values
- 전체 줄을 차지하지 않기에, 한 줄에 여러 요소 놓을 수 있음
- display: block;
- Takes up the entire line => so they can’t be centered

## Div

- Div: "Division"이라는 뜻임. 즉, 그냥 box같은 거임 (=Container)
- 장점: 걍 모든 element를 넣고, width/height를 변경해서 block 요소들을 한 덩어리로 만들 수 있음!!
- display: block; 인 element지만, 임의로 inline-block으로 변경 가능

## Grid

- [Grid]

- Grid: layout that has rows and columns (a X b)

- display: grid;
- grid-template-columns: 100px 1fr 2fr;
![img_5.png](img%2Fimg_5.png)
- => 위처럼 사용함. size는 각 칸의 width고, 반복되는 횟수는 column수임
-       (e.g., 100px 100px 200px는 column이 3개며, 각각의 width임)

- fr: 화면에 남는 공간을 차지함. 만약 1fr 2fr 라고 사용하는 경우, 각각의 요소가 1:2 비율로 화면에 남는 공간을 차지하게 됨.

## Flexbox

- [Flexbox]

- Flexbox: another way to create horizontal layouts while maintaining alignment
- expands to take up as much as space it need to => 말그대로 flexible한 box!!
- If there’s not enough space, it starts shrinking!!!
- shrinking하는 걸 막고, 위치가 그대로 고정되게 하려면 => flex-shrink: 0;
![img_2.png](img%2Fimg_2.png)
![img_3.png](img%2Fimg_3.png)
- => 위처럼 사용함. Grid와 다르게, Flexbox는 배치될 각 요소에 사용할 size를 지정해줘야 함
- Flex: 1; => grid의 1fr과 동일한 역할
- Justify-content: how these elements are aligned horizontally
- start, end, center, space-between
- align-items: how these elements are aligned vertically
- stretch, start, end, center

## Grid vs. Flexbox

- Grid vs. Flexbox
- Layout is more rigid for Grid => 이게 무슨 말이냐면, Grid는 parent div 내에 column의 수와 width를 지정하는데, Flexbox는 child div에 width property를 가져가기 때문에, child divs의 순서를 변경해도 grid처럼 각 div의 width가 rigid 하게 지정되지 않고 flexible함.

## CSS Display Properties (5)

- There are 5 CSS Display Properties:
- => 모두 top/bottom/left/right 사용

- position: static;
- DEFAULT (X affected by the top/bottom/left/right) => always positioned according to the normal flow of the page
- 다른 position 요소들과 비교했을 때, 항상 제일 back에 위치함 => z-index를 활용해 앞으로 빼주기!
- position: relative;
- position: fixed;
- 스크롤을 하더라도 항상 페이지의 같은 자리에 존재하며 따라옴
-            => element를 resize 하려면,
- If you want the fixed element to resize with the page => top/bottom/left/right에 stretch되길 원하는 pixel을 지정 (왜냐면, 만약 화면크기가 줄어들면, margin이기 때문에 떨어진 거리에 따라 요소의 크기도 함께 줄어들기 때문)
- If you want to have a specific height or width and you don’t want it to resize => height/width를 지정 (이렇게 하면, 화면 크기가 줄어들고 margin이 변경되더라도, 그 크기 그대로 fixed된 position에 요소가 붙어있게 됨)
- position: absolute;
- position: sticky;
- 화면에 고정되며 (스크롤하면 안 따라옴), 페이지 위로 붕 뜨므로 block이 inline 형태로 변경됨

- z-index: determines which elements appear in front and which elements appear behind (default value = 0)
- value가 클 수록, 화면 위에 떠 있음

## Fixed vs. Absolute

- Fixed vs. Absolute
- Fixed: placed in the browser window => 즉, 스크롤해도 특정한 자리에 계속 존재함
- Absolute: placed on the page => 즉, 특정 자리에만 붙어있으므로 스크롤해서

## Position: absolute; 를 효율적으로 쓰는 법

- Position: absolute; 를 효율적으로 쓰는 법:
- absolute가 붙은 element를 parent element 내에 넣게 되었을 때, parent element에 position: relative;를 부여하면, 해당 parent element의 position을 기준으로 top/right/bottom/left 값을 사용해 위치를 상대적으로 지정할 수 있음!
- Position: relative;가 아닌 parent element에 집어넣는 경우, top/right/bottom/left 값을 사용하게 되면 전체 page 기준으로 위치를 지정해야 함
- Parent element가 될 수 있는 요소는 container같은 것들임(div) => img같은 것들이 아님!!

## Position: fixed; 를 활용한 overlay 기법 (꿀팁)

- Position: fixed; 를 활용한 overlay 기법 (꿀팁):
- 만약 modal을 띄울 때 화면의 background를 조금 어둡게 조정하고 싶으면, Top, bottom, left, right = 0; background-color: rgba(0,0,0,0.8); 로, 배경색을 어둡고 투명한 요소로 overlay 해버릴 수 있음

## 자잘한 팁들

- [자잘한 팁들]

- <p> tag에는 기본적으로 margin-top과 margin-bottom이 지정되어 있음. 이것을 해제하려면 다음과 같이 setting하고 시작하면 됨:
-     p {
- margin-top: 0;
- margin-bottom: 0
-     }

- margin: auto; 는 horizontally center를 함! vertical-align: middle;은 vertically center를 함.

- [버튼1] [버튼2] [버튼3] 처럼 요소들이 수평으로 나열된 경우 => 만약 해당 버튼들의 높이가 모두 다르다면, 이는 browswer가 과거에는 text를 읽는 것이 main job이었기 때문에, 버튼을 text를 기준으로 align 하기 때문! 이 문제를 해결하려면:
- vertical-align: top/middle/bottom 같이 값을 부여해주면 됨

- 동일한 padding 및 margin을 가지는 두 버튼의 높이가 다를 때가 있는데, 그 이유는 border이 존재하는 버튼의 경우, border의 높이가 추가되기 때문임. 이를 해결하려면:
- padding이나 margin에 border-width를 빼거나 더해주면 됨

- 요소를 숨기려면:
- visibility: hidden;

- Shadow를 내부에 주는 방법:
- box-shadow: inset 10px 10px 1px black;

- placeholder에 css를 주는 방법:
- .search-bar::placeholder {
-     font-size: 16px;
- }

- 넘쳐흐른 요소를 감추는 법:
- overflow: hidden;

- box-model이란?
![img_4.png](img%2Fimg_4.png)