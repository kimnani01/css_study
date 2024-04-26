# CSS(Cascading Style Sheets)
## CSS 작성 전 준비사항
* html 문서 준비(태그 작성 완료 상태)
* html, css 파일 별도 폴더 관리
* 최상위 폴더 html 파일 배치
* 하위 폴더명 css, styles 으로 css 파일 배치
* ex) index.html, index.css
##  CSS 외부스타일시트와 내부스타일시트
* name.css 외부파일로 분리해서 html에 link로 연결한느 **외부 스타일시트**
* html파일 내에서 head태그 안에 style 태그로 구분해서 작성하는 **내부 스타일시트**
* 외부스타일시트 장단점 :
- 장점 : 1개의 css 파일로 여러개의 html을 관리할 수 있다.
- 단점 : 파일명 또는 파일 위치를 정확히 관리하지 않으면 파일관리가 어려울 수 있다.
* 내부스타일시트 장단점 :
- 장점 : html파일 내에 작성하여 태그와 한꺼번에 보기 편하다.
- 단점 : 2개 이상의 html파일을 동시에 디자인하는 것이 불가능하다.
## css 선택자
1. 태그선택자 : `<h1></h1>` -> `h1 {속성:값;}`
2. 클래스선택자 : `<h1 class="a"></h1>` -> `.a {속성:값;}`
3. 아이디선택자 : `<h1 id="b"></h1>` -> `#b {속성:값;}`
4. 자손선택자 :`<h1><em><span></span></em><h1>` -> `h1 em span {속성:값;}`
5. 자식선택자 : `<h1><em><em></em></em></h1>` -> `h1 > em {속성:값;}`
## CSS 디자인하기
* CSS 작성 전 HTML이 미리 디자인이 되어있으면 안된다.
* **HTML을 디자인 초기화하는 작업이 CSS 디자인 전 반드시 선행되어야 한다!!!**
* 초기화 CSS `reset.css` 공통파일(날짜나 프로젝트명 표기금지!)
# CSS 글자 표현 속성
## font-family
* 로컬글꼴(설치글꼴제공) 또는 웹 글꼴(추천)을 연결할 수 있다.
* "메인대표글꼴", "후보글꼴" (후보제한없음)
* 후보글꼴은 메인글꼴과 모양이 비슷한 글꼴로 연결해야 한다.
* 폰트 이름의 `+`는 공백을 의미한다.
* 글꼴 이름에 한글이나 공백이 있으면 `""`가 필요하다.
## font-size
* 웹 글꼴 평균 16px
* 사용 단위 px, %, em, rem
* 절대값 : px, 상대값 : %, em, rem(권장)
* em은 가장 가까운 부모를 기준
* rem은 body를 기준
## font-weight(폰트 두께)
# 선택자 우선 순위
* #아이디(3) > .클래스(2) > 태그(1)
1. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box .a .b p {}` 3+2+2+1 = 8
* `#box #a .b p {}` 3+3+2+1 = 9 가장 높음
* `#warp #box .a {}` 3+3+2 = 8 
* `#warp .a .b p {}` 3+2+2+1 =8
2. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box .a .b .c {}` 3+2+2+2 = 9
* `div .a .b .c {}` 1+2+2+2 = 7
* `.box p p .c {}` 2+1+1+2 = 6
* `div p p p {}` 1+1+1+1 = 4
## color
* 영문명 직접 입력 ex) 테스트용으로 주로 밝은색을 사용한다.
* aqua, lime, yellow, coral, ...
* 헥사코드 입력 최소값0 ~ 최대값F RGB 코드 기준
* RGB 웹 색상 기준으로 색상을 섞을 수록 밝아진다.
* #Hex #000000 == #000, #FF00CC => #F0C
* rgba(red, green, blue, alpha) *최대색상 255
* css에서 a(투명도)의 값은 0(0%) ~ 1(100%) 사이에 존재한다.
## line-heght(행간), letter-spacing(자간), word-spacing(단어 간격)
## text-align(정렬)
## 안쪽 여백 padding, 바깥쪽 여백 margin
* 시계방향 순서 Top → Right → Bottom → Left
* 마진 겹치는 값 오류, 나중에 선언한 값을 0, 먼저 선언한 값에 합친 마진 값 주기
* margin : 상하 좌우; (상=하, 좌=우)
* margin : 상 좌우 하; (상≠하, 좌=우)
## box css
### display
* `block, inline, inline-block`
* 특정 태그가 화면에 어떻게 표시될지 지정하는 속성
* `block` : 새로운 행, 크기, 여백 인식
* `inline` : 내용만큼 크기인식(그 외 크기인식 불가능)
* `inline-block` : 내용만큼 크기인식(크기 추가설정 가능), 옆으로 정렬
* a태그는 inline, block 특징을 모두 가질 수 있지만 고유한 속성은 inline이기 때문에 표시속성 display명령으로 block으로 변경하지 않는 한 크기, 여백을 제대로 인식하지 못한다.
### box-sizing
* `box-sizing: border-box`
* 요소의 너비와 높이를 계산할 때 테두리, 여백(padding)까지 포함해서 계산하는 속성
* 속성 미적용 시 : w100+h100+padding-top20 = 100x120
* 속성 적용 시 : w100+h100+padding-top20 = 100x100
### width, height
* 요소의 너비와 높이
* 절대값px, 상대값%, 화면 상대값 vw,vh
* 상대값 처리는 0~100% 사이 값만 사용한다.
### border-radius(모서리 둥글게)
* border-radius: 50%; (% 추천)
### shadow
* figma drop-shadow == css box-shadow
* box-shadow: x축 y축 blur값 색상;
## table(표)
* 테이블 관련 태그는 모두 블록 특징을 가지고 있다.
### tr 행, td 내용 열
* 열(td)은 항상 행(tr) 안에 존재해야 한다.
### thead, tbody, tfoot 행 그룹
* 행그룹은 행(tr)의 부모로 사용
* thead : 제목행그룹, th위주로 구성된 제목행을 묶을 때 사용
* tbody : 내용행 그룹, td위주로 구성된 내용행(tr)을 묶을 때 사용
* tfoot : 결과행그룹, th&td들로 구성된 결과값을 가지는 결과행(tr)을 묶을 때 사용
* tfoot을 쓸 경우 tbody보다 올려 쓴다. (스크린리더)
## form 요소와 속성
### `<form action="#" method=""></form>`
* action : 폼 데이터를 제출할 서버 스크립트 지정
* method : 폼 데이터를 제출하는 방법 (post:보안높음 / get:보안낮음)
### `<input type="" name="">`
* type : input 요소가 나타낼 입력 필드의 종류를 정한다.
* name : input 요소의 이름을 지정한다. (데이터 구분)
* readonly : 읽기전용
* autofocus, autocomplete : 커서 활성화, 자동완성
* value : 미리 제시된 텍스트
* placeholder : 미리 제시된 텍스트
* value와 palceholder의 차이점 : value는 활성화 시 제거가 안되고, placeholder는 활성화 시 제거된다.
* maxlength
### `<textarea></textarea>`
* rows, cols : 행, 열 글자 수를 정한다.
* 사용용도 및 주의 사항 : 폰트에 따라 영역크기가 달라질 수 있기 때문에 width, height를 사용하여 값을 정하는 것이 좋다.
### input의 입력양식과 선택양식
* text, url 등의 사용자가 직접 입력 가능한 입력양식
* radio 등의 사용자의 입력이 아닌 선택으로 들어가는 선택양식
* `name` : 입력양식(데이터구분용), 선택양식(데이터구분(개별데이터x, 그룹데이터 구분용))
* `value` : 입력양식(초기값), 선택양식(개별데이터 구분용)
## CSS Layout
### float, flex
* `float` : 형제 관계에 해당하는 block or inline tag 왼쪽, 오른쪽 정렬할 때 사용
* 예 : ul-li*3개 정렬 `ul li {float:left;}`
* `flex` : 정렬하고자 하는 아이템의 부모한테 flex를 먼저 설정한다.
* 예 : ul-li*3개 정렬 `ul {display:flex;}`
* flex 설정 시 **기본값** : 메인축(수평) 교차축(수직)
`display:flex` : 정렬대상의 부모 설정 속성값, 설정 시 해당 부모 기준 자식까지(자손x) flexible box layout으로 처리하겠다!
### 자식에 float 적용함으로써 생기는 부모인식 오류 해결
* 해결법 1. 크기를 직접 적용한다. (height: 100px;)
* 해결법 2. 자식 포함 크기재인식 속성 (overflow: hidden;)
* 해결법 3. 가상요소생성 (::after {clear:both;`float를 제거` content:'';`빈 문자열` display: block;`가상요소의 표현속성`})
### flex : container(부모)에 적용하는 속성
* flex-directon : container 안의 item의 메인축 방향 설정
* flex-warp : container 내부 items 줄바꿈 처리 설정
* flex-flow :  flex-direction과 flex-wrap을 묶음으로 처리
- `flex-flow: 메인축방향 줄바꿈 속성;`
- flex를 쓸 때는 자식에 height와 line-height를 같이 쓰는 경우가 많다
* justify-content : 메인축의 **정렬방법**을 설정
* align-content : 교차축의 아이템이 **2줄 이상**일 경우 정렬방법 (flex-warp:warp 적용한 상태)
- **flex-warp:wrap** 적용한 상태에서 해야한다
* align-items : 교차축의 아이템이 **1줄**일 경우 정렬방법
### flex : item(자식)에 적용하는 속성
* align-self : container(부모)에 적용하는 align-items보다 우선순위가 높다
* order : 아이템의 정렬 순서 설정. 태그순서와 상관없이 order로 정렬순서를 변경가능
* flex : 증가/감소/기본의 묶음속성