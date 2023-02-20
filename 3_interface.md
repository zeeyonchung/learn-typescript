## 변수에 인터페이스 활용
```
interface User {
  age: number;
  name: string;
}

let gildong: User = {
  age: 30,
  name: 'Gildong',
};
```


## 함수의 인자에 인터페이스 활용
```
function logUser(user: User): void {
  console.log(user);
}

logUser({
  age: 100,
  name: 'Julie',
});
```


## 함수의 구조에 인터페이스 활용
```
interface SumFunction {
  (a: number, b: number): number;
}

let sum: SumFunction;
sum = function (a: number, b: number): number {
  return a + b;
};
```


## 인덱싱 방식에 인터페이스 활용
```
interface StringArray {
  [index: number]: string;
}

let arr: StringArray = ['a', 'b', 'c'];
console.log(arr[0]); // 'a'
```


## 인터페이스 딕셔너리 패턴
```
interface StringRegexDictionary {
  [key: string]: RegExp;
}

let obj: StringRegexDictionary = {
  sth: /abc/,
  cssFile: /\.css$/,
  jsFile: /\.js$/,
};

console.log(obj.sth);
// obj.cssFile = 'a'; //Error
```


## 인터페이스 확장
```
interface Person {
  age: number;
  name: string;
}

interface Developer extends Person {
  language: string;
}

let dev: Developer = {
  age: 25,
  name: 'Josh',
  language: 'C',
};
```