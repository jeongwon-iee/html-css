
<img width="778" alt="스크린샷 2020-10-05 오후 3 49 00" src="https://user-images.githubusercontent.com/45806836/95048133-4b631800-0722-11eb-8849-d902e0bbbc98.png">


# 해야할 것

줄간격 조정

 p태그 길이 제한

input, buttom 꾸미기

x 버튼 우측 상단에

모달 화면의 정가운데에

# `index.html`

`aside` 태그: 전체 웹 페이지에 관계된 내용 Ex. modal, 사이드바 메뉴

```html
<!doctype html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>position-3</title>
        <link href="https://fonts.googleapis.com/css?family=Nunito+Sans:400,600&display=swap" rel="stylesheet" />
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <aside class="modal">
            <button class="close-button" type="button" aria-label="닫기"></button>
            <h1 class="modal-title">Manage Subscriptions</h1>
            <p class="modal-desc">
                You can follow the discussion on @jeongwonlee without to leave a comment. Cool, huh? Just enter your email address in
                the form here below and you are all set.
            </p>
            <div class="input-group">
                <input type="email" placeholder="Your e-mail">
                <button type="submit" aria-label="구독">Subscribe</button>
            </div>
        </aside>
    </body>
</html>
```

# `style.css`

## 줄간격 조정

```css
.modal-title {
    font-size: 24px;
    font-weight: 600;
    line-height: 1.6666666667;
    text-align: center; //가운데 정렬
    margin-bottom: 4px;
}
```

## p태그 길이 제한

```css
.modal-desc {
    width: 590px;
    font-size: 16px;
    line-height: 1.5;
}
```

## 모달 화면의 정가운데에

```css
.modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    padding: 32px 40px;
    border-radius: 4px;
}
```

## x 버튼 우측 상단에

position이 static이 아닌 부모 요소를 기준으로 → modal 이 이미 fixed니까 조정할 필요x

```css
.close-button {
    position: absolute;
    top: 8px;
    right: 8px;
}
```

---

# 결과


<img width="778" alt="스크린샷 2020-10-05 오후 3 49 00" src="https://user-images.githubusercontent.com/45806836/95048133-4b631800-0722-11eb-8849-d902e0bbbc98.png">
