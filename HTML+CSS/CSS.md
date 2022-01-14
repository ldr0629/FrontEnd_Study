# CSS Basic and Syntax

## CSS
웹 브라우저와 웹 페이지를 사용하는 사람과 웹 페이지에 대한 컨텐츠를 생산하는 저자가 서로 조화를 이뤄 웹을 만들어 간다라는 철학을 구현할 수 있는 기능으로 선택된 언어이다.

HTML이 웹페이지의 정보를 표현한다면, CSS는 HTML을 보기 좋게 디자인하는 역할을 한다. 즉, HTML은 정보에 중심을 둔다면, CSS는 스타일과 관련된 기능에 중심을 두고있다.

### CSS 삽입 방법
- body 태그로 감싸진 곳에 있는 태그 내에서 "style" 속성을 이용하여 css 코드를 작성한다.

'''html
<h1 style="color:blue">CSS</h1>
'''

- head 태그로 감싸진 곳에서 <'style'> 태그를 이용하여 body 태그 내에 있는 태그의 스타일적인 부분들을 꾸며주는 코드를 작성한다. 

'''html
<style>
    h1 {  
        color:red; 
    }
</style>
'''

### 선택자
특정 태그를 디자인하기 위해서 디자인하려는 태그를 
1. 선택하고 (선택자)
2. 선택한 대상에게 효과를 준다. (선언)

- <'head'> 태그 내에서 <'style'> 태그로 감싸준 후 디자인을 바꾸고자 하는 태그명{ css코드(속성:속성 값) } 형태는 태그 선택자이다.

- 아이디 속성의 값에 해당하는 태그를 선택하는 아이디 선택자는 특정 태그 내에 id의 속성 값을 명시해주고 id명에 <'head'> 태그 내에서 #을 붙여 사용하면 그 특정 태그만을 디자인해준다.

- 클래스 속성의 값에 해당하는 태그들을 선택하는 선택자 클래스 선택자는 특정 태그 내에 class의 속성 값을 지어주고 속성값을 <'head'> 태그 내에서 .을 붙여 사용하면 그 클래스 값에 속한 태그들을 디자인해준다. "class" 라는 속성은 같은 태그뿐만 아니라 서로 다른 태그도 그룹핑하여 묶어줄 수 있다.

- 어떤 값들을 그룹핑시킬 때 class라는 속성을 이용하는 것이고, id 선택자는 한번 정했으면 똑같이 두 번 이상 사용하면 안된다.

- 이외에는 전체 선택자(*)와 속성 선택자도 있다. 

**주의사항** <br>
css 효과를 두가지 이상 줄 경우 하나의 효과를 나타내는 코드를 작성한 후 이를 구분해주기 위해 세미콜론(;)을 붙여주어야 한다.

#### 부모-자식 선택자
어떤 태그의 하위에 있는 태그를 선택하여 스타일링 하고 싶을 때 

1. 조상 자손 선택자
- 어떤 태그의 밑에 있는 모든 태그를 선택한다.

'''html
<style>
    ul li {
        font-size:15px;
    }
</style>
'''

2. 부모 자식 선택자
- 어떤 태그의 바로 밑에 있는 태그들만 선택한다.

'''html
<style>
    ol > li {
        font-size:15px;
    } 
</style>
'''

3. 형제 선택자
- 두 개 이상의 태그의 밑에 있는 태그들을 포함하여 스타일링을 해주고 싶은 경우 사용한다.

'''html
<style>
    ul, ol {
        font-size:15px;
    } 
</style>
'''

#### 가상 클래스 선택자
클래스 선택자는 아니지만 엘리먼트들의 상태에 따라서 마치 클래스 선택자처럼
여러 엘리먼트를 선택할 수 있다는 점에서 붙은 이름이다.

- 사용 형태는 "태그명:엘리먼트의 상태" 로 명시해주고 스타일링해주면 가상으로 클래스 선택자처럼 선택할 수 있다.

**링크와 관련된 가상 클래스 선택자** <br>
- :link - 방문한 적이 없는 링크
- :visited - 방문한 적이 있는 링크
- :hover - 마우스를 roll over 했을 때 
- :active - 마우스를 클릭했을 때 
- :focus - 탭 키를 눌렀을 때 해당 태그의 내용을 가르키게 되며 엔터를 눌렀을 때 그 링크로 이동한다.

>> :visited의 경우는 보안상의 이유로 아래와 같은 속성만 변경이 가능하다.
- color
- background-color
- border-color
- outline-color

#### 우선순위
하나의 웹 페이지가 여러 디자인의 영향을 받을 수 밖에 없으므로 우선순위를 정해야한다.

하나의 태그에 중첩해서 CSS가 적용됐을 때에 세부적인 우선순위는 다음과 같다.

> tag selector < class selector < id selector < style attribute <br>
가장 포괄적이고 일반적인 선택자일수록 우선순위에서 낮아지고, 구체적인 선택자 및 속성일수록 우선순위에서 높아진다.

모든 것을 무시하고 우선순위에서 가장 높게하려면 선택자 선언에서 "!important"를 넣어주면 1순위로 적용된다.

### CSS Property

**font & text** <br>
- font-size : 글꼴의 크기를 지정하는 속성이며 font size에서 사용할 수 있는 대표적 단위로는 px, em, rem이 있다.

1. px
모니터 상의 화소 하나의 크기에 대응되는 단위. 고정된 값이기 때문에 이해하기 쉽지만, 사용자가 글꼴의 크기를 조정할 수 없기 때문에 가급적 사용을 하지 않는 것이 좋다. 

2. em
부모 태그의 영향을 받는 상대적인 크기. 부모의 크기에 영향을 받기 때문에 파악하기가 어렵다. rem이 등장하면서 이 단위 역시 사용이 권장되지 않는다. 

3. rem
html 태그의 폰트 크기에 따라서 상대적으로 크기가 결정되기 때문에 이해하기 쉬우며, 가장 바람직한 단위. 또한, 폰트 크기를 조정할 수 있는 사용자의 권리가 있기때문에 이것을 주로 사용한다.

- font-family : 글꼴을 지정하는 방법이며, 비슷한 폰트들을 묶어서 우선순위에 따라 더 선호하는걸 먼저 보여주려한다. 마지막 폰트는 포괄적인 폰트로 지정한다.
serif (장식이 있는 폰트), sans-serif, cursive (흘림체), fantasy, monospace (고정폭)과 같은 것들이 있다.

- font-weight : 폰트의 두께를 표현하는 방법이고, bold 값이 있다.

- line-height : 글자의 행과 행 사이의 간격을 조정하는 방법으로, 기본 값은 1.2이다.

- color : 글꼴의 컬러를 지정할 수 있으며, color name, hex(16진수), rgb 세가지 방법 중 하나를 이용해 지정한다. font뿐만 아니라 background-color(배경 색), border-color(테두리 색)로 속성을 지정해줄 수도 있다.

[사용 방법](https://www.w3schools.com/css/css_colors_rgb.asp)

- text-align : 텍스트를 정렬하는 속성이다. 속성 값으로 left, right, center, justify이 있다. 이외에도 들여쓰기를 하고자 할 때 text-indent, 텍스트를 꾸미고 싶을 때는 text-decoration을 사용한다.

**box** <br>
- border : 테두리를 만들고 싶을 때 쓰는 속성이며, width, style, color 순으로 작성한다. 둥근 모서리 테두리를 만들고 싶을 때는 border-radius가 사용되며 이미지로 테두리를 생성하는 속성은 border-image이다.

- padding : 테두리와 텍스트 간 간격을 주고싶을 때 쓰는 속성이다.

- margin : 테두리와 테두리 간(or 브라우저 틀 간) 간격을 주고싶을 때 쓰는 속성이다.
   
- background-image : 배경의 이미지를 지정해주는 속성으로 이미지의 url을 설정해주어야 한다. 배경 이미지 위치 지정할 때 -position이 붙으며, 배경 이미지 반복 여부에 대한 것은 -repeat이 붙는다.

- width, height : 태그의 너비와 높이를 지정해주는 속성이다.

- box-sizing : 박스의 크기를 화면에 표시하는 방식을 변경하는데, border의 두께로 인해서 어떤 엘리먼트의 크기를 예측하기가 까다로워지는 상황이 발생하기 때문에 이러한 문제를 해결하기 위하여 사용한다.

기본 값으로 지정하면 컨텐츠의 크기만큼 width와 height 값이 지정되고, box-sizing의 값을 border-box로 바꾸면 border의 두께가 동일해진다. 이때 컨텐츠 블록의 크기를 예측하기 쉬워진다.

**effect** <br>
- transform : 엘리먼트의 크기, 위치, 모양을 변경하는 속성으로, scale, translate, rotate, skew, matrix 등이 있다.

display가 block 엘리먼트 또는 inline-block인 상태일 경우에만 적용한다. 

- transition : 효과가 변경되었을 때 부드럽게 처리해주는 기능이다.

1. property : 어느 효과가 변경되었을 때 전환되는지 지정해주는 속성.

2. duration : 전환되는 데 걸리는 시간을 지정.

3. timing-function: transition이 적용될 때의 속도를 커스터마이징하는 속성.
ease-out, ease-in-out, ease(def), linear 등이 있다.

4. delay : 시간을 지연시킬 때 쓰는 속성

- animation : css 스타일과 keyframes로 구성되며, transition보다 규모가 크고 복잡하며 정밀한 효과를 구현 할 수 있다.

***규칙*** <br>
1. 적용될 대상은 @keyframes 이 반드시 붙어야 한다.
2. transition과 다르게 가상 선택자나 js 없이도 실행이 가능하다.

다음은 animation의 속성 종류이다.

animation-name : @keyframes 이름 <br> 
animation-duration : 실행 시간 <br> 
animation-timing-function : 가속, 감속설정 <br> 
animation-delay: 실행 지연시간 <br> 
animation-iteration-count : 재생 횟수 <br> 
animation-direction : 재생 방향 <br> 
animation-fill-mode : 종료 후 상태 (forwards: 100% 도달 후 키프레임 유지) <br> 
animation-play-state : 재생/정지 

특정 애니메이션에 대해 from(0%), to(100%) 또는 %로 작성하면 된다.

**layout** <br>
- position : 각각의 엘리먼트들의 위치를 지정하는 방식과 관련있는 속성이며, 기본 값은 static이다.

1. relative : left, right, top, bottom의 값에 따라 부모 태그로부터 값만큼 떨어진 포지션을 지정할 수 있다.

2. absolute : body 태그 기준으로 값을 지정해 포지션을 변경시킬 수 있다. 부모 자식 관계가 사라진다.

absolute의 경우에는 부모 태그의 position이 static이 아닌 형태가 되면 그 부모 태그를 기준으로 포지션이 변경된다.

3. fixed : 특정한 엘리먼트를 화면상 위치에 고정시켜서 스크롤로부터 완전히 독립되게 할 수 있다. 부모 태그와 관계는 없다.

- float : 이미지를 삽화로 삽입할 때 사용하는 기법이고, 레이아웃을 잡을 때 사용하는 기능이다.

이미지와 동등한 위치에서 텍스트를 삽입하고 싶은 경우 img 태그에 float 속성을 넣어 방향값을 지정해주면 된다.

특정 텍스트를 나타내는 태그에 대해서는 동등한 위치에 놓이고 싶지 않은 경우 특정 태그 내 style 속성 값으로 "clear:both" 값을 적용한다.

- flex : 엘리먼트들의 크기, 위치를 쉽게 잡아주는 도구로써, 레이아웃을 효과적으로 표현할 수 있다. 각각의 요소들을 자유롭게 정렬하는 방법이다.

***parent*** <br>
flex는 부모와 자식으로 유지되며, 부모 container에 display 값으로 flex를 주어야 한다. "flex-direction"을 통해 정렬 방향을 바꿀 수 있다. 정렬 값에는 row, column, -reverse이 있다.

1. flex-wrap : 한줄에 차지하는 줄바꿈 방식 설정해준다. nowrap(모든 요소들을 한 줄에 정렬), wrap(요소들을 여러 줄에 걸쳐 정렬), wrap-reverse(wrap의 반대로 정렬)이 있다.

2. justify-content : 가로로 정렬하는 방식이며, flex-start(왼쪽 정렬), flex-end(오른쪽 정렬), center(가로선 상 가운데 정렬), space-between(요소 사이에 동일한 간격), space-around(요소 주위에 동일한 간격)이 있다. 이와 반대로는 세로 정렬 방식으로 align-content, align-items도 있다.

3. order: 차지하는 박스의 우선순위를 지정해준다.

4. flex-flow : flex-direction과 flex-wrap를 같이 쓰는 대신 축약형으로 사용할 수 있다.

***child*** <br>
item에 적용하는 속성으로 flex-basis는 정렬 방향에 따른 아이템의 크기를 지정해줄 수 있다.

flex-grow는 1을 주게되면 컨테이너 크기에 따라 똑같은 비율로 아이템들이 크기를 차지하고, 특정 아이템에 대해 비율을 늘릴 수 있다. 

flex-basis로 크기가 지정된 아이템일때 flex-shrink를 통해 웹 페이지 사이즈를 조정했을 때에도 크기가 줄어드는 것을 막을 수 있다. 이때 속성값은 0이다.

- grid : flex 보다 정교하고 복잡한 레이아웃을 구현할 때 쓰는 속성이다 페이지를 여러 주요 영역으로 나눌 때 사용된다.

1. grid-template-columns(rows) : repeat() 함수 또는 직접 지정 틀에 맞춰 열 또는 행의 구간을 나눠준다. repeat 함수의 auto-fit은 화면을 꽉 채워 칼럼 너비를 맞춰주며. auto-fill은 칼럼 최소 너비만큼 채워준다. 여기에 사용되는 minmax 함수는 최소 픽셀을 지정해주는 함수이다.

2. grid-template-areas : box에 대한 위치를 문자열로 지정해준 이후 개별 박스에 대해 grid-area를 지정한다.

3. grid-column(row) : > 비율에 맞춰 크기를 나눠준다. (어느정도 차지하는지 사이즈/전체 박스 개수)

4. grid-gap : 컬럼 간격 및 행 간격을 지정해준다.


### Box model
- 각각의 태그들이 웹 페이지에 표현될 때 그 태그의 부피감을 결정해준다. "display" 속성을 통해 지정해줄 수 있다.

**inline element** <br>
- 자신을 둘러싸고 있는 다른 텍스트나, 다른 정보들과 하나의 같은 줄에 위치하는 형태의 태그이다.

- 화면의 일부를 차지하는 태그로, a 태그와 같이 하이퍼링크를 텍스트에 다는 경우나 span 태그가 예가 될 수 있다.

**block element** <br>
- 오직 자기 혼자서 화면 전체를 다 쓰는 태그이다. ex. h1 같은 제목 태그의 경우나, 하나의 블록을 차지하는 div 태그일 때 혼자 쓰는 것이 합리적인 편이다.

**inline-block element** <br>
- 차지하는 태그 크기에 대해 width, height를 직접 지정해줄 수 있는 태그로 display의 값이 inline-block이어야 한다.