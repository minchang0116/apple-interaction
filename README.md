# apple-interaction
ECMA 2015(ES6) 기반의 애플 웹사이트 인터랙션 효과 클론코딩


## 2021-06-10 (목)
#### 1. 웹페이지 골격 만들기
- 메뉴 스타일링
<!-- ![menu](https://user-images.githubusercontent.com/36808530/121535288-fc9e1880-ca3c-11eb-808e-6676ec7d0074.png) -->
<img src="https://user-images.githubusercontent.com/36808530/121535288-fc9e1880-ca3c-11eb-808e-6676ec7d0074.png" width="700">

- AirMug Pro 옆의 영역 차지하기
```
.local-nav-links .product-name {
  margin-right: auto;
  font-size: 1.2rem;
}
```


- flex </br>
Flex 아이템들은 가로 방향으로 배치되고, 자신이 가진 내용물의 width 만큼만 차지 </br>
height는 컨테이너의 높이만큼 늘어남 </br>
https://studiomeal.com/archives/197

- css 우선순위 </br>
1) 속성 값 뒤에 !important를 붙인 속성
2) HTML에서 style을 직접 지정한 속성
3) #id로 지정한 속성
4) .클래스, :추상클래스로 지정한 속성
5) 태그 이름으로 지정한 속성
6) 상위 객체에 의해 상속된 속성

```
.local-nav-links .product-name {
  margin-right: auto;
  font-size: 1.2rem;
}

.local-nav-links a {
  font-size: 0.8rem;
}

위에 작성한 코드가 우선순위가 더 높음
```


## 2021-06-25 (금)
- 메뉴 스타일링 2

```
.local-nav-links a:not(.product-name) {
  margin-left: 2em;
}
```
local-nav-links의 a인데 클래스가 product-name인 것을 빼고 적용한다.

- 페이지 내용 HTML 작성
```
		<section class="scroll-section" id="scroll-section-0">
			<h1>AirMug Pro</h1>
			<div class="sticky-elem sticky-elem-canvas">
				<canvas id="video-canvas-0" width="1920" height="1080"></canvas>
			</div>
			<div class="sticky-elem main-message a">
				<p>온전히 빠져들게 하는<br>최고급 세라믹</p>
			</div>
			<div class="sticky-elem main-message b">
				<p>주변 맛을 느끼게 해주는<br>주변 맛 허용 모드</p>
			</div>
			<div class="sticky-elem main-message c">
				<p>온종일 편안한<br>맞춤형 손잡이</p>
			</div>
			<div class="sticky-elem main-message d">
				<p>새롭게 입가를<br>찾아온 매혹</p>
			</div>
		</section>
```

일반적으로 스크롤되는 것이 아닌 스크롤 영역에 딱 붙어있는 요소들을 stick-elem class로 붙여줬다.

<!-- ![image](https://user-images.githubusercontent.com/36808530/123382275-b44e3100-d5cc-11eb-8c8f-c83ee3af8739.png) -->
<img src="https://user-images.githubusercontent.com/36808530/123382275-b44e3100-d5cc-11eb-8c8f-c83ee3af8739.png" width="700">

- 페이지 내용 CSS 작성 1
```
.scroll-section {
  padding-top: 50vh;
}
#scroll-section-0 h1 {
  font-size: 4rem;
  text-align: center;
}
.main-message {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 5px 0;
  height: 3em;
  font-size: 2.5rem;
}
.main-message p {
  font-weight: bold;
  text-align: center;
  line-height: 1.2;
}
```
50vh : 인터넷 브라우저 창의 높이의 절반만큼이다.
이번 프로젝트는 CSS는 mobile first로 작성할 것이다.

rem(root em)은 최상위 요소인 html요소에 비례하여 크기를 가지는 상대적인 길이를 말한다.
즉 html요소에 font-size를 고정값으로 지정해두면 그 비율에 따라 크기가 계산된다.
rem은 IE9버전까지 지원이 된다.

```
.main-message {
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 5px 0;
  height: 3em;
  font-size: 2.5rem;
}
```
font-size는 rem으로 하고 height은 em으로 주는 이유는
현재 컨텍스트에서 font-size에 대한 비율을 쓰기위해 하는 것이다.
즉, height은 2.5rem의 3배이다.

![image](https://user-images.githubusercontent.com/36808530/123385865-fb3e2580-d5d0-11eb-99c9-4dab05d0f0b7.png)

- 페이지 내용 CSS 작성 2
