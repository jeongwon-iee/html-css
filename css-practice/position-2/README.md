<img width="596" alt="스크린샷 2020-10-05 오후 2 23 35" src="https://user-images.githubusercontent.com/45806836/95042958-5c0d9100-0716-11eb-9612-18399707e601.png">

# 해야할 것

카드 사이즈 조정

화살표 사진에 부착

줄간격 조정

가격 카드 하단에 부착

# `index.html`

 `***span***` 비어있는 태그! 문장에서 사용

`span` 태그는 ***문장의 특정 구역에 CSS스타일을 지정할 때 사용!***

`div` 의 역할과 비슷하지만, `div` 태그는 사각형 박스 모양으로 구역을 지정하고, `span`은 *한 문장 단위*다.

---

# `style.css`

## 카드 사이즈 조정

```css
.travel-card {
	width: 400px;
}
```

⇒ 부모인 카드 크기를 조정했는데 이미지에는 적용되지 않음

```css
.travel-card {
	width: 400px;
}

.photo-card img {
	width: 100%; // 부모 width에 맞추기
	height: auto; // 자신의 원래 비율대로 
}
```

- image는 display값이 inline이지만 특수하게 width, height 값을 가질 수 있지만 display를 block으로 변환

```css
.photo-card img {
	display: block; // display를 block으로 변환
	width: 100%; 
	height: auto; 
}
```

## 화살표 사진에 부착

화살표가 영역을 차지 하지 않고, 붕 띄워서 이미지에 부착 해야함 → position

- relative: 원래 있던 위치를 기억하기 때문에 소용 x
- fixed: viewport를 기준으로 하지 않기 때문에 소용 x
- absolute 사용!

`position: absolute;` 사용 시 ***기준점 설정!***

자신이 속한 부모 중 position이 static이 아닌 요소를 기준으로 설정

→ 기준: photo-card

```css
.photo-card {
    position: relative;
    background-color: #E5EAEF;
}

#prev,
#next {
    position: absolute; 
    top: 50%; // photo-card 기준 50% 위치
}

#prev {
    left: 0;
}

#next {
    right: 0;
}
```

photo-card 기준 50% 위치 시켰는데 정중앙이 아님 → 50%에서부터 놓여짐

### `transform` 기준: 자기 자신

- rotate() 회전시킬 때
- scale() 확대 축소
- translate(x, y) 위치를 이동시킬 때 사용

⇒ 위쪽으로 올려줘야함 `translateY(-50%)`  = 자기 자신의 반만큼 올라가라

```css
#prev,
#next {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
}
```

## 줄간격 조정

h1에 margin-bottom 주기

```css
.card-content h1 {
    margin-bottom: 2px;
}
```

## 가격 카드 하단에 부착

`span` 과 `strong` 태그 모두 display 값이 inline이라 가로 배치가 되어있음

가격을 카드 하단으로 떨어뜨리기 위해 `strong`의 display를 block으로

⇒ margin-top 사용(bottom/top 통일하는 게 일반적이나 `span`은 inline이라 bottom을 줄 수 없어 `strong`에서 top을 줌

글자들이 너무 카드 테두리에 붙어있음 ⇒ card-content에 padding 주기

---

# 결과

<img width="596" alt="스크린샷 2020-10-05 오후 2 23 35" src="https://user-images.githubusercontent.com/45806836/95042958-5c0d9100-0716-11eb-9612-18399707e601.png">
