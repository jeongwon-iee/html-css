
<img width="538" alt="스크린샷 2020-10-04 오후 5 08 45" src="https://user-images.githubusercontent.com/45806836/95010436-450e6680-0664-11eb-8f6a-06170f5a8be5.png">

글자들 간 간격 조정

이미지 사이즈와 모양 조정

이미지와 텍스트 카드 가로배치

이미지와 텍스트 카드 간격 주기

전체 카드에 여백 주기

# `index.html`

```html
<!doctype html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>float-2</title>
    <link href="https://fonts.googleapis.com/css?family=Noto+Sans+KR&display=swap" rel="stylesheet" />
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="card">
        <img src="assets/user.jpg" alt="customer-support" class="img-user">
        <div class="card-content">
            <h1>RE: 안녕하세요. 배송 관련 문의 드립니다.</h1>
            <strong>customer support</strong>
            <p>안녕하세요 정원님. 문의 드린 사항에 대한 답변 드립니다. 지난 11...</p>
        </div>
    </div>
</body>
</html>
```

# `style.css`

`clearfix` 라는 가상 클래스를 만들어 float 한 번에 잡아준 후 HTML 파일에서 부모 요소에 clearfix class 추가

```css
* {
    box-sizing: border-box;
    margin: 0;
}

body {
    font-family: "Noto Sans KR", sans-serif;
    letter-spacing: -0.02em;
    height: 100vh;
    background-color: #bfc2cc;
}

h1 {
    font-size: 16px;
    font-weight: 400;
    color: #1f2d3d;
    line-height: 1.25;
}

strong {
    font-size: 14px;
    font-weight: 400;
    color: #afb3b9;
    line-height: 1.4285714286;
}

p {
    font-size: 16px;
    color: #79818b;
    line-height: 1.5;
}

.clearfix::after {
    content: '';
    display: block;
    clear: both;
}

.card {
    max-width: 540px;
    padding: 20px;
    background-color: #ffffff;
}

.img-user {
    width: 44px;
    height: 44px;
    border-radius: 50%;
    margin-right: 20px;
}

.card-content h1{
    margin-bottom: 4px;
}

.card-content strong {
    display: block;
    margin-bottom: 12px;
}

.img-user,
.card-content {
    float: left;
}
```

# 결과

<img width="602" alt="스크린샷 2020-10-04 오후 5 10 12" src="https://user-images.githubusercontent.com/45806836/95010462-79822280-0664-11eb-88df-ba222ecaeec3.png">

