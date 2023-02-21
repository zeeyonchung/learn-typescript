# 타입 가드
```
interface Developer {
    name: string;
}

interface Person {
    name: string;
    age: number;
}

function introduce(): Developer | Person {
    return {
        name: 'Tony',
        age: 30,
        skill: 'Iron Making',
    };
}

let tony = introduce();
console.log(tony.name); // Tony
console.log(tony.skill); // Error! 유니온타입의 공통된 타입만 접근 가능

if ((tony as Developer).skill) {
    console.log(tony.skill); // Iron Making
}
else if ((tony as Person).age) {
    console.log(tony.age); // 30
}
```
코드가 중복되고 가독성이 떨어지므로 이렇게 쓰는 것은 좋지 않다. 타입 가드를 사용해서 개선할 수 있다.

```
function isDeveloper(target: Developer | Person): target is Developer {
    return (target as Developer).skill !== undefined;
}

if (isDeveloper(tony)) {
    console.log(tony.skill); // Iron Making
}
else {
    console.log(tony.age); // 30
}
```
보통 isXXX 형식의 이름을 사용한다.  
(흠 사실 개선된 건지 잘 모르겠다...)