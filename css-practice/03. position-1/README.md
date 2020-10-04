<img width="458" alt="스크린샷 2020-10-04 오후 6 11 42" src="https://user-images.githubusercontent.com/45806836/95011643-1052dd00-066d-11eb-930d-105e00a81d77.png">


이미지 사이즈 조정, 원 모양으로 변경

상태 동그라미 만든 후 이미지 우측 하단에 부착

이미지와 유저 이름 가로 배치

유저 카드에 여백, border 둥글게

---

# `index.html`

```html
<!doctype html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0">
        <title>position-1</title>
        <link href="https://fonts.googleapis.com/css?family=Lato&display=swap" rel="stylesheet" />
        <link rel="stylesheet" href="./style.css" />
    </head>
    <body>
        <div class="user-card">
            <div class="user-photo">
                <img src="assets/user.jpg" alt="user-photo">
                <span class="user-status" aria-label="Active"></span>
            </div>
            <h1 class="user-name">Jeongwon Lee</h1>
        </div>
    </body>
</html>
```

# `style.css`

## 이미지 사이즈 조정, 원 모양으로 변경

image는 display: inline이어도 width와 height가 작동됨.

→ `display: block` 으로 변경

## 상태 동그라미 만든 후 이미지 우측 하단에 부착

```css
.user-status {
    display: block;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    border: 2px solid #ffffff;
    background-color: #21DB91;
}
```

width와 height를 줬는데도 브라우저 상에서 보이지 않음

→ `display: block` 으로 변경

- 우측 하단에 부착하기

: 원래 있던 자리에서 벗어나 이미지 우측 하단에 붙어야 함 → absolute

> viewport 기준 → fixed
완전히 다른 위치로 → absolute
현재 위치에서 → relative

```css
.user-status {
		position: absolute;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    border: 2px solid #ffffff;
    background-color: #21DB91;
}
```

position이 absolute라면 display는 block이니 지워도 됨

absolute는 자신의 조상 요소들 중 static이 아닌 요소를 기준으로 잡아 이동됨.

기준: user photo. ⇒ user-photo에게 `position: relative;` 줌

```css
.user-status {
		position: absolute;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    border: 2px solid #ffffff;
    background-color: #21DB91;
}
```

## 이미지와 유저 이름 가로 배치

```css
.user-photo,
.user-name {
    float: left;
}

.usercard::after {
    content: '';
    display: block;
    clear: left;
} 
```

가상 클래스 만들기!

- 유저 이름 가운데 정렬 (padding으로 할 것)

```css
.user-name {
    padding: 8px 0;
}
```

## 유저 카드에 여백, border 둥글게

```css
.user-card {
    width: 240px;
    padding: 8px 12px;
    border: 1px solid #E5EAEF;
    border-radius: 4px;
}
```

⇒ float는 그냥 가로 배치를 위해, position은 특정 위치를 위해 사용

---

# 결과

<img width="458" alt="스크린샷 2020-10-04 오후 6 11 42" src="https://user-images.githubusercontent.com/45806836/95011643-1052dd00-066d-11eb-930d-105e00a81d77.png">
