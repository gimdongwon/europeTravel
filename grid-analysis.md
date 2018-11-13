# **grid project분석**

1. 모든 부분을 container로 감싼다. => 전체 영역이 960px로 잡혀 있고  모바일 화면을 반응형 웹지자인 으로 구성하기 위해서 container를 활용한다.

2. 그림내 글자에서 줄바꿈을 하려면 무조건 p태그를 이용해서 2개를 만들어서 이용.

3. 웹폰트 및 외부 폰트를 지정하는 법

`@import url(https://spoqa.github.io/spoqa-han-sans/css/SpoqaHanSans-kr.css);`

`@import url(https://spoqa.github.io/spoqa-han-sans/css/SpoqaHanSans-jp.css);`

- 허나 지금 로컬에서 폰트를 돌리는 것이 안된다. 못 찾았다. 이건 질문해보자 ㅠㅠ

=> 해결했다. 이름이 잘못 지정되 있엇음..... 슈발 인제 안까먹는다
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<title>font-test</title>
	<link rel="stylesheet" href="ress.css">
	<style>
	/*@import url(https://spoqa.github.io/spoqa-han-sans/css/SpoqaHanSans-kr.css);*/
		
		h1{
			font-family: "SpoqaHanSans";
		}
	</style>
</head>
<body>
	<h1 class="font-test">이것은 Spoqa폰트	입니다.</h1>
	<h1>이것은 일반 폰트 입니다</h1>
	<h1 >하하하<span>호호호</span></h1>
</body>
</html>
```
4. linear-gradient의 속성의 첫 번째는
	1. 방향성
	2. 투명도 transparent
	3. 마지막 0.4는 투명도가 40%라는 뜻을 가진다 
		
		고로 "선형 그림자효과를 줄건데 아래방향으로 가고 투명도는 40%를 유지하며 검은색 느낌을 줘!" 라는 뜻을 가진다. 

		`linear-gradient(to bottom, transparent, rgba(0,0,0,0.4)) ;`

5. 이미지 배치시에 정가운데로 배치하고 싶으면 

	`background-position: center center;
		background-size: cover;`

6. 이미지 안에 있는 text 왼쪽 하단으로 떨어 뜨리기

	`display: flex;
	flex-direction: column;
	justify-content: flex-end;`

7. 동영상 넣기는 다시 한번 복습하자

8. 그리드 시스템 적용하기 

```
[class*="col-"]{
float: left;
padding: 0 10px 0 10px;
}
.row::after{
content: '';
display: block;
clear: both;
}
.col-1{width: 8.33%}
.col-2{width: 16.67%}
.col-3{width: 25%}
.col-4{width: 33.33%}
.col-5{width: 41.67%}
.col-6{width: 50%}
.col-7{width: 58.33%}
.col-8{width: 66.67%}
.col-9{width: 75%}
.col-10{width: 83.33%}
.col-11{width: 91.67%}
.col-12{width: 100%}
}
```

9. 반응형 디자인은 모바일 화면을 100%를 설정하여 태블릿화면과 데스크탑화면만 남겨서 