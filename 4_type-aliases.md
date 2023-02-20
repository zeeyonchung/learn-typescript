## 인터페이스
```
interface Person {
  age: number;
  name: string;
}
```

## 타입
```
type Person = {
  age: number;
  name: string;
};
```

## 사용하기
```
let julie: Person = {
  age: 20,
  name: "Julie",
};
```

## 타입 별칭
```
type MyString = string;
let str: MyString = "hello";
```

타입 별칭은 새로운 타입 값을 생성하는 것이 아니라 나중에 쉽게 참고할 수 있게 이름을 부여하는 것이다.
타입은 확장이 불가능하지만 인터페이스는 확장이 가능하다. 따라서, 가능한 한 인터페이스로 선언해 사용한다.
