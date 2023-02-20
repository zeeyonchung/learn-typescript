# js 프로토타입
클래스를 쓰는 이유를 체감하기 위해 자바스크립트 프로토타입에 대해 알아보겠다.
```
// 객체 속성의 중복
var user = {
  name: 'Jane',
  age: 25
};

var admin1 = {
  name: 'Jane',
  age: 25,
  role: 'admin'
}

// 중복을 피하기 위한, 프로토타입을 이용한 상속
var admin2 = {};

admin2.__proto__ = user;
console.log(admin2.name, admin2.age); //Jane, 25

admin2.role = 'admin'
console.log(admin2.role) //admin
```
### Build-in Javascript API / Javascript Native API
```
var obj = { a: 10 };
console.log(obj.hasOwnProperty()); //true
```
위 코드에서 obj의 프로토타입은 Object이다. 그래서 Object에 정의된 메서드를 사용할 수 있다.