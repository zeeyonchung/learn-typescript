# 타입 단언
```
let a;
a = 10;
let b = a as string;
```
"타입스크립트보다 개발자가 타입을 더 잘 알고 있다. 그러니 개발자가 시키는대로 타입을 간주해라."

### DOM API 조작
```
let div = document.querySelector('div');

if (div) { // div의 타입은 HTMLDivElement | null
    div.innerText = 'Hello World';
}
```
위 코드를 아래처럼 쓸 수 있다.
```
let div = document.querySelector('div') as HTMLDivElement;
div.innerText = 'Hello World';
```