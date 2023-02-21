## 숫자형 이넘
별도의 값을 지정하지 않으면 숫자형 이넘으로 인식된다. (0부터 시작)
```
enum Shoes1 {
  Nike,
  Adidas,
}

let myShoes1 = Shoes1.Nike;
console.log(myShoes1); // 0
```

## 문자형 이넘
```
enum Shoes2 {
  Nike = '나이키',
  Adidas = '아디다스',
}

let myShoes2 = Shoes2.Nike;
console.log(myShoes2); // 나이키
```

## 이넘의 활용
```
function askQuestion1(answer: string): void {
  if (answer == 'yes') {
    console.log('정답입니다');
  }
  if (answer == 'no') {
    console.log('오답입니다');
  }
}

enum Answer {
  Yes = 'yes',
  No = 'no',
}

function askQuestion2(answer: Answer): void {
  if (answer == Answer.Yes) {
    console.log('정답입니다');
  }
  if (answer == Answer.No) {
    console.log('오답입니다');
  }
}
```