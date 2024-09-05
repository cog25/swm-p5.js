---
theme: default
colorSchema: dark
drawings:
  persist: false
transition: slide-left
mdc: true
fonts:
  sans: Freesentation
  serif: KoPubBatang
  mono: D2Coding
  provider: none
lineNumbers: true
---

<svg viewBox="0 0 28 28" xmlns="http://www.w3.org/2000/svg" fill="none" ><path d="M16.909,10.259l8.533-2.576l1.676,5.156l-8.498,2.899l5.275,7.48 l-4.447,3.225l-5.553-7.348L8.487,26.25l-4.318-3.289l5.275-7.223L0.88,12.647l1.678-5.16l8.598,2.771V1.364h5.754V10.259z" fill="currentColor"></path></svg>

# p5.js

## 시작하기

20901 강태웅(23_stu0501@guri.hs.kr) <br/>

<div class="flex gap-2">

<a href="https://github.com/cog25/swm-p5.js" class="color-transparent hover:!color-transparent">

![See in Github](https://img.shields.io/badge/-See%20in%20Github-181717?style=flat-square&logo=github)

</a>

<a href="https://stackblitz.com/github/cog25/swm-p5.js/tree/main/template?title=2024%20SWM%20p5.js%20실습&file=src/sketch.js" class="color-transparent hover:!color-transparent">

![Open in StackBlitz](https://img.shields.io/badge/-Open%20in%20StackBlitz-1269D3?style=flat-square&logo=stackblitz)

</a>


</div>

<style> 
  h1 { @apply font-800; }
  svg { @apply max-w-10em absolute right-5em animate-spin animate-duration-15s; }
  /* p { @apply text-align-end } */
</style>

---

## 일정

| 날짜  | 내용          |
| ----- | ------------- |
| 9/6   | p5.js - Day 1 |
| 9/27  | p5.js - Day 2 |
| 11/01 | 자유주제발표  |
| 12/20 | 1학년 발표    |

---

## p5.js란

<v-clicks>

공식 홈페이지에 따르면...

> p5.js is a friendly tool for learning to code and make art. It is a free and open-source JavaScript library built by an inclusive, nurturing community. p5.js welcomes artists, designers, beginners, educators, and anyone else!

p5.js는 코딩과 예술 제작을 배우기 위한 친숙한 도구입니다. 포용적이고 육성적인 커뮤니티에서 구축한 무료 오픈소스 JavaScript 라이브러리입니다. 아티스트, 디자이너, 초보자, 교육자 등 누구나 p5.js를 사용할 수 있습니다!

</v-clicks>

<style> { blockquote { @apply m-be-8; } } </style>

---

## 무얼 할수 있을까?

<v-clicks>

- **인터랙티브 아트**
  - 사용자의 움직임에 반응하는 예술 작품, 움직이는 추상 그림, 음악에 맞춰 변하는 시각 효과 등 다양한 형태로 표현됩니다.
- **게임 개발**
  - 단순한 아케이드 게임부터 복잡한 시뮬레이션 게임까지, p5.js를 활용하여 다양한 게임을 제작할 수 있습니다.
- **데이터 시각화**
  - 복잡한 데이터를 시각적으로 이해하기 쉽게 표현하는 데 유용합니다. 데이터 분석 결과를 시각적으로 보여주는 프로젝트를 만들 수 있습니다

</v-clicks>

---

## 알아야 할것!


- 자바스크립트 기반이다 <v-click> ➡️ 자바스크립트에 대한 기초 문법 </v-click>

<v-clicks depth=2>

- 우리는 이미 알고 있습니다
- Playbot은 약간 변형*된 자바스크립트 문법을 차용
  - 예) 변수 선언, 메시지 출력

</v-clicks>

---
class: text-center font-bold text-2em
---

# 빠르게 복습 && 모르는 내용 배우기


---

## 변수 선언

```js {all|1-2|4-5}
// 기존
변수명 = 1;

// 원래 자바스크립트 문법
let 변수명 = 1;
```

---

## 상수 선언

```js {all|1|3-4}
const 상수명 = 123;

const PI = 3.14;
// 상수명은 관습적으로 대문자로 표기
```

---

## 출력하기

```js {all|1|2|3}
console.log(1 + 3, 5);
console.log(-0.1)
console.log("안녕, p5.js");
```

---


```js {all|1|3|4}
const PI = 3.14;

console.log("반지름이 3인 원의 넓이는")
console.log(3*3*PI, "입니다")
```

---
layout: two-cols
---

## 산술 연산자
사칙연산과 같은 작업을 하는 연산자

<v-click>

- `+`: 덧셈
- `-`: 뺼셈
- `*`: 곱셈
- `/`: 나눗셈
- `%`: 나머지

</v-click>

::right::

<v-click>

```js {all|3|4|5|6|7}
const A = 10, B = 20;

console.log(A + B);
console.log(A - B);
console.log(A * B);
console.log(A / B);
console.log(A % B);
```

</v-click>

---

## 대입 연산자
특정 값에 연산을 한 값을 바로 설정

````md magic-move
```js 
let a = 10;
a = a + 5;

let b = 10;
b = b - 5;

let c = 10;
c = c * 5;

let d = 10;
d = d / 5;

let e = 10;
e = e % 5;
```
```js
let a = 10;
a += 5;

let b = 10;
b -= 5;

let c = 10;
c *= 5;

let d = 10;
d /= 5;

let e = 10;
e %= 5;

```
````

---

```js {all|1-2|4-5|7-8}
a = 10;
console.log(a); // 10

a += 10;
console.log(a);

a /= 10;
console.log(a);
```

---

## 비교 연산자
두 값 중에서 무엇이 더 크고 작은지 비교
```js {all|1-3,5|1-3,6|1-3,7|1-3,8|1-3,9}
const a = 10;
const b = 15;
const c = 15;

console.log(a < b); 
console.log(b > a); 
console.log(b >= c); 
console.log(a <= c);
console.log(b < c); 
```

<!--
마지믹 뻬거\ㅗ \\\ 침
-->

---

## 논리 연산자

<v-clicks>

> $a$는 $10$보다 크거나 같고 $20$보다 작다

$$ 
10 \leq a < 20 
$$

- 컴퓨터는 멍청해서 연립 부등식을 풀이 X

$$
a \geq 10 \text{ 그리고 } a < 20
$$

</v-clicks>

---

```js {all}
console.log(10 <= a < 20)
// 작동 안함
console.log(10 <= a && a < 20)
```

---
class: text-left
---


## 문자열 붙이기
```js {1|2|1-2|3}
const a = '안녕';
const b = '하세요';
console.log(a + b); // 안녕하세요
```

---

## 원래는... 조금 더 배워야 하지만

<v-clicks>

- 함수(Function)
- 배열(Array)
- 반복문(Loop)
- Class
- 등등...

**아직 너무 많이 남아서.. 실습하면서 필요할때 보충합시다**

</v-clicks>

<style>
h2 { @apply text-center block }
</style>

---

## 실습 시작하기

1. 다음 주소에 Chrome으로 접속
> https://p5js.swm.cog.moe/

2. 이렇게 생긴 버튼 클릭

> ![Open in StackBlitz](https://img.shields.io/badge/-Open%20in%20StackBlitz-1269D3?style=flat-square&logo=stackblitz)

<style>
  img[alt="Open in StackBlitz"] {
    @apply h-2em;
  }
</style>

<!-- 
 다음: 파란색으로 된 Fork 버튼 클릭

 -->