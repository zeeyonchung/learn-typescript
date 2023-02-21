# 타입 호환
```
interface Avengers {
    name: string;
}

class Ironman {
    name: string;
}

let i: Avengers;
i = new Ironman(); // OK
```
Ironman 클래스가 명시적으로 Avengers 인터페이스르르 상속받아 구현하지 않았지만 정상적으로 동작한다.  자바스크립트는 명시적으로 지정된 타입이 아니라 코드의 **구조 관점**에서 서로 호환되는지 여부를 판단한다. (구조적 타이핑 structural typing)

### 인터페이스 호환
```
interface Person {
    name: string;
}

interface Developer {
    name: string;
    skill: string;
}

let developer: Developer;
let person: Person;
developer = person; // Error!
person = developer; // OK
```
### 함수 호환
```
let add = function(a: number) {
    // ...
}

let sum = function(a: number, b: number) {
    // ...
}

add = sum; // Error!
sum = add; // OK
```
### 제네릭 호환
```
interface Empty<T> {
    value: string;
}

let empty1: Empty<string>;
let empty2: Empty<number>;

empty1 = empty2; // OK
empty2 = empty1; // OK
```
```
interface NotEmpty<T> {
    data: T;
}

let notempty1: NotEmpty<string>;
let notempty2: NotEmpty<number>;

notempty1 = notempty2; // Error!
notempty2 = notempty1; // Error!
```