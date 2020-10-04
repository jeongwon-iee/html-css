<img width="685" alt="스크린샷 2020-10-04 오후 2 52 48" src="https://user-images.githubusercontent.com/45806836/95008062-46826380-0651-11eb-82d4-174ef348eaad.png">

# `index.html` 

`!` + `tab` ⇒ html 스크립트 자동 완성

unordered list에 list item이 네 개

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>float-1</title>
        <link href="https://fonts.googleapis.com/css?family=Roboto:400,500&display=swap" rel="stylesheet" />
        <link rel="stylesheet" href="./style.css" />
    </head>
    <body>
        <ul>
            <li>
                <a href="#">Summary</a>
            </li>
            <li>
                <a href="#">Emails</a>
            </li>
            <li>
                <a href="#">Files</a>
            </li>
            <li>
                <a href="#">Mentions</a>
            </li>
        </ul>
    </body>
</html>
```

# `style.css`

## 해야할 것

- 없애기

불필요한 왼쪽 padding 없애기

메뉴 아이템 가로 배치

각 메뉴 아이템 간 간격 주기

각 메뉴 아이템 패딩 주기

메뉴 아이템들 밑 연한 회색 border

선택 되었을 때 border 주기, font 색상 변경

---

## class 지정

`ul` 에는 `tab-menu` 라는 클래스를, `list item` 에는 `tab-menu-item` 클래스 지정

## list style

`list-style-type` 속성으로 `circle` `square` `decimal` 등을 줄 수 있음

```css
ul {
	list-style-type: none;
}
```

## 불필요한 왼쪽 padding 없애기


```css
ul {
	list-style-type: none;
	padding-left: 0;
}
```

## `tab-menu-item` 들 가로 배치

가로 배치를 하는 방법

- inline 요소는 옆으로 흐르니까 가로 배치를 할 수 있다

    ⇒ 위 아래 padding을 줄 수 없어 탈락

- inline block

    ⇒ 가능

- float

    ⇒ 가능

```css
.tab-menu-item {
    float: left;
}
```


개발자 도구에서 `tab-menu` 를 확인해보면 자식들이 전부 float 되어서 자식을 찾지 못 하고 있음 

### ***⇒ CSS로 가상 요소 만들기  `부모::after`***

자식인 가상 요소를 하나 만들면 부모가 float된 자식들을 찾을 수 있다.

*가상 요소 (`::before`, `::after`) 사용 시 `**content**` 주기!* 

### float 된 자식들을 찾기 위해 써야 하는 `clear`

⇒ `float: left;` 니까 `clear: left;` 로 주기

`*clear` 사용 시 `**display: block;**`*

```css
.tab-menu::after {
		content: '';
    display: block;
    clear: left;
}
```


⇒ `tab-menu` 에 가상 요소 `::after` 가 생기고, 높이가 생겼음 (자식을 찾음)

## 각 메뉴 아이템 간 간격 주기

```css
.tab-menu-item {
    float: left;
    margin-right: 16px;
}
```

## 각 메뉴 아이템에 패딩 주기

위아래로 16, 양 옆으로 20px 줄 것.

list item이 아닌 ***anchor에 padding을 줘야*** target 영역이 넓어짐

*그런데! anchor는 display: inline이라 padding-top, padding-bottom 불가*

<a>에 위아래 padding 주려면 `**display: block/inline block**`

```css
.tab-menu-item a {
    display: block;
    padding: 16px 20px;
}
```


## 메뉴 아이템들 밑 연한 회색 border

menu 전체 밑에 border가 있으니 `tab-menu` 에. 굵기, 모양, 색상 줘야 함

```css
.tab-menu {
    border-bottom: 1px solid #E5EAEF;
}
```


## 선택 되었을 때 border 주기, font 색상 변경

선택된 Emails에 `active` 라고 클래스를 따로 주고

```css
.tab-menu-item.active {
    border-bottom: 2px solid #2860e1;
}

.tab-menu-item.active a {
    font-weight: 500;
    color: #2860e1;
}
```

