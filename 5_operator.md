## 유니온타입
```
function logMessage(value: string | number): void {
  console.log(value);

  if (typeof value === 'number') {
    value.toLocaleString();
  }
  else if (typeof value === 'string') {
    value.toString();
  } 
  else {
    throw new TypeError('value must be string or number');
  }
}

logMessage('hello');
logMessage(100);
```

```
interface Person {
  name: string;
  age: number;
}

interface Developer {
  name: string;
  skill: string;
}
```
  

유니온타입의 경우 공통된 속성에만 접근 가능하다.
```
function askSomeone1(someone: Developer | Person): void {
  console.log(someone.name);
  // console.log(someone.age);  //Error
  // console.log(someone.skill); //Error
}
```

## 인터섹션 타입
```
// Developer와 Person의 속성 모두를 포함하는 타입
function askSomeone2(someone: Developer & Person): void {
  console.log(someone.name);
  console.log(someone.age);
  console.log(someone.skill);
}
```