# Generics
```
// JS
function logText(text) {
    console.log(text);
    return text;
}

// TS
function logText<T>(text: T): T {
    console.log(text);
    return text;
}

logText(10);
logText('Hello World');
logText(true);
```

## 제네릭의 장점
```
function logText(text: string): string {
    console.log(text);
    return text;
}

function logNumber(num: number): number {
    console.log(num);
    return num;
}
```
위 코드처럼 단지 다른 타입을 전달 받기 위해서 중복된 코드를 생산하는 문제를 해결한다.  
물론 아래처럼 유니온타입을 사용할 수도 있지만, 이 때의 문제는 반환값의 타입도 유니온타입이라는 것이다.
```
function log(text: string | number) {
    console.log(text);
    return text:
}

const a = log('a'); // a의 타입은 string | number이다!
a.split(" "); // Error! 그래서 이런 코드를 쓸 수 없다, string과 number에 공통으로 존재하는 메서드만 사용 가능하다.
```

## 인터페이스에 제네릭 적용하기
```
// Before
interface Dropdown {
    value: string;
    selected: boolean;
}

// After
interface Dropdown<T> {
    value: T;
    selected: boolean;
}

const obj: Dropdown<number> = {
    value: 10,
    selected: false,
};
```

## 제네릭의 타입 제한
```
// 배열로 제한하기
function logTextLength<T>(text: T[]): T[] {
    console.log(text.length);
    return text;
}
```
```
// 정의된 타입으로 제한하기
interface Length {
    length: number;
}

function logTextLength<T extends Length>(text: T): T {
    console.log(text.length);
    return text;
}

logTextLength(10); // Error!
logTextLength('a'); // 문제 없다! 문자열에는 이미 length라는 속성이 있기 때문이다 WOW
logTextLength({ length: 10 }); // OK
```
```
// keyof를 사용해서 제한하기
interface Item {
    name: string;
    price: number;
    stock: number;
}

function extract<T extends keyof Item, Item>(key: T, item: Item): Item[T] {
    return item[key];
}

console.log(extract('name', { name: 'Hat' })); //Hat
console.log(extract('price', { price: 100 })); //100
```
`T extends keyof Item`의 의미: "Item의 속성 중 한 가지의 키가 제네릭이 된다" - 즉 'name', 'string', 'stock' 중 한 가지를 인자로 전달할 수 있다.