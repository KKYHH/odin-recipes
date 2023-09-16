# THE ODIN PROJECT

<img src="https://github.com/KKYHH/odin-recipes/assets/102516350/bccc320a-f32b-466f-a1e8-46a169c07d9e" width="400" height="200">

# odin-recipes
https://www.theodinproject.com/lessons/foundations-recipes


# GitHub Pages
GitHub Pages 기능으로 웹페이지 호스팅


https://kkyhh.github.io/odin-recipes/



<p align="center">
<img src="https://user-images.githubusercontent.com/102516350/266851628-b8c033dd-515a-4e61-b999-19446497c4fb.png" width="350" height="350">
<img src="https://user-images.githubusercontent.com/102516350/266863829-99ec9426-9d05-4c6d-8f3d-21e5fae8edfc.png" width="350" height="350">
<img src="https://user-images.githubusercontent.com/102516350/266863839-927043e6-2f8a-49c6-bb10-7a60532843e6.png" width="350" height="350">
<img src="https://user-images.githubusercontent.com/102516350/266851634-619dc8e0-c94f-417e-ac10-704fca925b0b.png" width="350" height="350">
</p>


___
# 설명

오딘 프로젝트의 CSS Foundations와 Flexbox를 통해서 기본적인 웹 레이아웃을 알아본다

**Intro to CSS**
- https://www.theodinproject.com/lessons/foundations-intro-to-css

**Introduction to Flexbox**
- https://www.theodinproject.com/lessons/foundations-introduction-to-flexbox


>중간중간마다 있는 설명 링크나 과제,지식체크,추가 리소스 부분들의 정보들이 도움이 된다

>생각날 때 마다 들어와서 다시 읽어보기

___

# 기록

## ✅ background
background-image를 사용 할 때 url을 상대경로로 넣어줘야 배포에 문제가 없다
절대경로로 사용하면 찾지를 못한다

``` html
/images/burger.jpg X
../images/burger.jpg O
```

```css
background-image: url("")
background-size: cover;
background-position: center;
background-repeat: no-repeat;
background-attachment: fixed;
```
- size : cover : 전체 컨테이너를 덮도록 이미지 크기를 조정
- position : center : 이미지를 중앙에 배치
- repeat : no-repeat : 이미지를 한번만 표시한다
- attachment : fixed : 배경 이미지가 스크롤 되지 않도록 고정한다



## ✅ media query

미디어 쿼리 없이 웹 호스팅을 하고나니 데스크탑 노트북 모바일에서 화면들이 제 각각 따로 깨져버린다는걸 확인했다

https://coding-factory.tistory.com/938
<img src="https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FCl39l%2Fbtshy6DIA80%2F6IG9PmUxUuLHXAnWE6c5F1%2Fimg.png" >


테스트용 페이지의 각 이미지 파일들의 크기가 전부 달라서 개발자도구로 확인하며 조절을 해줬다

```css
      @media (max-width: 1600px) {
        img {
          width: 50%;
          height: auto;
        }
      }

      @media (min-width: 1600px) {
        img {
          width: 20%;
          height: auto;
        }
      }
```
데스크탑과 노트북 태블릿 사이에서 화면 크기와 이미지를 조절


```css
      @media (max-width: 480px) {
        .mid {
          height: auto;
          margin: 0;
          padding: 0;
          font-size: 16px;
          display: flex;
          flex-direction: column;
          justify-content: center;
          align-items: center;
        }
      }
```
모바일용 페이지에서는 구조 전체를 변경했다 당연하게도 화면이 작기 때문에 column이 들어가는게 맞아보였다


## ✅ Flexbox

`display : flex` 의 시작

처음 CSS를 봤을 때 무엇인지도 모르고 남발하던 flex를 완벽은 아니지만 무엇인지는 알게 되었다

<p align="center">
<img src="https://cdn.statically.io/gh/TheOdinProject/curriculum/495704c6eb6bf33bc927534f231533a82b27b2ac/html_css/v2/foundations/flexbox/imgs/03.png" width="600" height="200">

<img src="https://cdn.statically.io/gh/TheOdinProject/curriculum/495704c6eb6bf33bc927534f231533a82b27b2ac/html_css/v2/foundations/flexbox/imgs/04.png" width="600" height="200">

<img src="https://cdn.statically.io/gh/TheOdinProject/curriculum/495704c6eb6bf33bc927534f231533a82b27b2ac/html_css/v2/foundations/flexbox/imgs/05.png" width="600" height="200">
</p>




https://flexbox.malven.co/

flex의 기능을 위 페이지에서 한 눈에 확인 할 수 있다

<br>
<br>


```css
justify-content
```
- flex의 주축 메인축을 움직인다



```css
align-items
```
- flex의 교차축 서브축을 움직인다

```css
flex-basis : ~ px
```
- flexbox의 기본 크기를 결정한다

```css
flex-grow 
```
- flexbox내의 남는 여백의 분배 비율을 정한다

```css
flex-shrink 
```
- flexbox내의 부족한 여백을 어떻게 각출할지 정한다
- ex) shrink를 0으로 설정하면 화면이 줄어들어도 본래의 크기가 고정된다

> flex-basis: 이 속성은 플렉스 아이템의 초기 크기를 나타냅니다. 기본값은 auto이며, 이 경우 아이템의 크기는 아이템의 내용에 따라 자동으로 조정됩니다. 그러나 flex-basis에 특정한 값 (예: 픽셀, 백분율)을 할당할 수도 있으며, 이 값은 초기 크기로 사용됩니다.

> flex-grow: 이 속성은 플렉스 아이템이 부모 컨테이너 내에서 얼마나 빠르게 증가할 수 있는지를 나타냅니다. 값이 0보다 큰 경우, 아이템은 여유 공간을 채우기 위해 크기를 확장합니다. 값이 클수록 확장 속도가 더 빠릅니다. 기본값은 0입니다.

> flex-shrink: 이 속성은 플렉스 아이템이 부모 컨테이너 내에서 얼마나 빠르게 축소할 수 있는지를 나타냅니다. 값이 0보다 큰 경우, 아이템은 너무 작은 경우에 크기를 축소합니다. 값이 클수록 축소 속도가 더 빠릅니다. 기본값은 1입니다.

> 따라서 이러한 속성은 0 또는 양의 숫자일 수 있으며, 이를 통해 플렉스 아이템의 동작을 조절할 수 있습니다. 값이 0인 경우 해당 속성의 작용이 없습니다. 값이 양의 숫자인 경우, 해당 속성에 대한 영향이 더 큽니다. 이를 통해 플렉스 레이아웃을 더 정밀하게 제어할 수 있습니다.

```css
flex-wrap
flex-wrap : wrap
flex-wrap : no-wrap
```
- flex 주축 방향으로 더 이상 공간이 없으면 튀어나가지 않고 교차축 방향으로 이동하게 감싸준다

> nowrap (기본값): 모든 플렉스 아이템을 한 줄에 나열하려고 시도하며, 만약 너비가 부족하면 아이템을 줄이지 않고 축소시킵니다. 즉, 아이템들이 한 줄로 오버플로우 될 수 있습니다.

> wrap: 플렉스 아이템을 여러 줄로 나눕니다. 화면의 너비를 벗어나면 아이템이 다음 줄로 넘어갑니다. 이것은 아이템들을 줄바꿈하여 여러 행에 걸쳐 표시할 때 유용합니다.

> wrap-reverse: wrap과 유사하지만 아이템들을 역순으로 나열합니다. 즉, 오른쪽에서 왼쪽 방향으로 줄 바꿈이 발생합니다.

> flex-wrap을 사용하면 플렉스 레이아웃의 유연성을 향상시킬 수 있습니다. 예를 들어, 가로로 넓은 공간에 아이템을 나열하다가 화면이 좁아질 때 아이템을 여러 줄로 나눌 수 있습니다. 이것은 다양한 화면 크기와 장치에 대응하여 레이아웃을 조정하는 데 도움이 됩니다.

<br>
<br>

공부할 겸 재미 삼아 만들어 봤지만 정렬하는 것은 제대로 알고 싶었다
이렇게 별 볼일 없는 구조를 짜보는데 순수하게 처음부터 해보려 하니 쉽지 않았다
이전까지는 얼렁뚱땅 CSS를 가져와서 쓰기도 하고 베끼면서 쓰기도 하다 보니 아는 것이 많이 없었기에

```css
display:flex;
justify-content:center;
align-items:center;
flex-direction: column;
text-align: center;

많이 쓴 CSS
```

여기선 중앙 정렬 위주의 레이아웃으로 컨테이너를 구성했지만 다음 프로젝트는 성배 레이아웃으로 시도해 본다



