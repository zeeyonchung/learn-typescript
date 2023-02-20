# js 클래스
```
class Person {
  constructor(name, age) {
    console.log('생성자');
    this.name = name;
    this.age = age;
  }
}

let gildong = new Person('길동', 30);
console.log(gildong);
```
Class라는 것은 syntax를 추가한 것일 뿐이고, 기존의 자바스크립트의 특성은 그대로이다.  
위 코드는 아래의 코드와 완전히 같다.
```
function Person(name, age) {
    this.name = name;
    this.age = age;
}

var gildong = new Person('길동', 30);
```

# ts 클래스
```
class Person {
    private name: string;
    public age: number;
    readonly log: string;

    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }
}
```
- 변수의 접근제어자를 설정할 수 있다. 
    - private, protected, public(default)
    - readonly
    - static