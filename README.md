# apple-interaction
ECMA 2015(ES6) 기반의 애플 웹사이트 인터랙션 효과 클론코딩


## 2021-06-10
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
