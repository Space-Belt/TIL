## ๐ฐ Clock

---

![แแตแแจ](https://user-images.githubusercontent.com/82592845/160370103-0e289fa6-493c-4f22-82de-4a6df82c50c4.gif)

---

```jsx
// hand hour-hand ์์นจ
// hand second-hand ์ด์นจ
// hand min-hand ๋ถ์นจ

<div class="clock">
  <div class="clock-face">
    <div class="hand hour-hand" id="hour"></div>
    <div class="hand second-hand"></div>
    <div class="hand min-hand"></div>
  </div>
</div>
```

```jsx
// CSS

.hand {
      width: 50%;
      height: 6px;
      background: black;
      position: absolute;
      top: 50%;
      transform-origin: 100%;
      transform: rotate(90deg);
      transition: all 0.05s;
      transition-timing-function: cubic-bezier(0.18, 2.58, 0, 2.21);

```

- transform-origin : ์์์ ๋ณํ์ ๋ํ ์์ 
  - rotate()ํจ์ ์ ๋ณํ ์์  ์ ํ์  ์ค์ฌ์๋๋ค.
  - [https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin)
- transform: rotate(90deg); ์คํ ํ๋ ค๊ณ  ๋ง๋ฌ.
- [https://www.codingfactory.net/10953](https://www.codingfactory.net/10953)

> ์ด์นจ, ๋ถ์นจ, ์์นจ์ ๊ฐ ๋ณ์์ ๋ฃ์ด์ค๋ค.
> (secondHand, minsHand, hourHand)

```
const secondHand = document.querySelector(".second-hand");

const minsHand = document.querySelector(".min-hand");

const hourHand = document.querySelector(".hour-hand");
```

> ํ์ฌ์๊ฐ์ ๋ฐ์์จ๋ค.( ์๊ฐ, ๋ถ, ์ด)

```
const now = new Date();
const seconds = now.getSeconds();
const mins = now.getMinutes();
const hours = now.getHours();
```

> ์๋ถ์ด์นจ์ด ์์ง์ผ ํจ์๋ฅผ ๋ง๋ ๋ค.
> secondHand๋ณ์์ style ์ transform์ ์ถ๊ฐํ๋ค.

```
function setDate() {
  const now = new Date();

  const seconds = now.getSeconds();
  const secondsDegrees = (seconds / 60) * 360 + 90;
  secondHand.style.transform = `rotate(${secondsDegrees}deg)`;

  const mins = now.getMinutes();
  const minsDegrees = (mins / 60) * 360 + 90;
  minsHand.style.transform = `rotate(${minsDegrees}deg)`;

  const hours = now.getHours();
  const hourDegrees = (hours / 12) * 360 + 90;
  hourHand.style.transform = `rotate(${hourDegrees}deg)`;
}
```

[https://curryyou.tistory.com/185](https://curryyou.tistory.com/185) ๋ฐฑํฑ (``` ) ์ฌ์ฉ๋ฒ

๋ฐฑํฑ์ผ๋ก ํํ์์ ์ฝ์ํ์ฌ ์ ํด์ค๋ค.

```
setInterval(setDate, 1000);
```

1. setInterval ์ฌ์ฉ ํด์ ์คํ

- [https://offbyone.tistory.com/241](https://offbyone.tistory.com/241)
- ์๋ฐ์คํฌ๋ฆฝํธ๋ก ์ฃผ๊ธฐ์ ์ธ ์์์ ์คํํ๊ธฐ ์ํด์ setInterval๊ณผ setTimeout ๋ฉ์๋๋ฅผ ์ฌ์ฉํ  ์ ์์ต๋๋ค. ๋ ๊ฐ์ง๋ ๋น์ซํ์ง๋ง ์ค์ํ ์ฐจ์ด์ ์ ๊ฐ์ง๋๋ค.
- **setInterval ํจ์**ย : ์ผ์ ํ ์๊ฐ ๊ฐ๊ฒฉ์ผ๋ก ์์์ ์ํํ๊ธฐ ์ํด์ ์ฌ์ฉํฉ๋๋ค.clearInterval ํจ์๋ฅผ ์ฌ์ฉํ์ฌ ์ค์งํ  ์ ์์ต๋๋ค. ์ฃผ์ํ  ์ ์ ์ผ์ ํ ์๊ฐ ๊ฐ๊ฒฉ์ผ๋ก ์คํ๋๋ ์์์ด ๊ทธ ์๊ฐ ๊ฐ๊ฒฉ๋ณด๋ค ์ค๋๊ฑธ๋ฆด ๊ฒฝ์ฐ ๋ฌธ์ ๊ฐ ๋ฐ์ํ  ์ ์์ต๋๋ค.
- **setTimeout ํจ์**ย : ์ผ์ ํ ์๊ฐ ํ์ ์์์ ํ๋ฒ ์คํํฉ๋๋ค. ๋ณดํต ์ฌ๊ท์  ํธ์ถ์ ์ฌ์ฉํ์ฌ ์์์ ๋ฐ๋ณตํฉ๋๋ค. ๊ธฐ๋ณธ์ ์ผ๋ก setInterval ๊ณผ๋ ๋ฌ๋ฆฌ ์ง์ ๋ ์๊ฐ์ ๊ธฐ๋ค๋ฆฐํ ์์์ ์ํํ๊ณ , ๋ค์ ์ผ์ ํ ์๊ฐ์ ๊ธฐ๋ค๋ฆฐํ ์์์ ์ํํ๋ ๋ฐฉ์์๋๋ค. ์ง์ ๋ ์๊ฐ ์ฌ์ด์ ์์ ์๊ฐ์ด ์ถ๊ฐ ๋๋ ๊ฒ์๋๋ค. clearTimeout() ์ ์ฌ์ฉํด์ ์์์ ์ค์งํฉ๋๋ค.
- **clearInterval(), clearTimeout()**์ด ์คํ์ค์ธ ์์์ ์ค์ง์ํค๋ ๊ฒ์ ์๋๋๋ค. ์ง์ ๋ ์์์ ๋ชจ๋ ์คํ๋๊ณ  ๋ค์ ์์ ์ค์ผ์ฅด์ด ์ค์ง ๋๋ ๊ฒ์๋๋ค.
