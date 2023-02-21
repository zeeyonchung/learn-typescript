# 타입 추론
```
let x = 3;
```
타입을 지정하지 않아도 x의 타입은 number로 추론된다.

```
function getB(b = 10) {
    return b;
}
```
b의 default 값을 10으로 지정하여 b의 타입이 number로 추론된다.

```
interface Dropdown<T> {
    title: string;
    value: T;
}

interface DetailedDropdown<T> extends Dropdown<T> {
    description: string;
    tag: T;
}

let item: DetailedDropdown<string> = {
    title: 'abc',
    description: 'abcdef',
    value: 'a',
    tag: 'a',
};
```
Dropdown value의 타입이 string으로 추론된다.
