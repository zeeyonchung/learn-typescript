# learn-typescript

## Getting started
- 확장자 `.ts`
- `.ts` 파일을 `.js` 파일로 변환하는 컴파일이 필요하다.
    ```bash
    npm i typescript -g #typescript 패키지 설치
    tsc index.ts #컴파일 -> index.js 생성됨
    ```
- `tsconfig.json`: 컴파일 설정 파일 (https://www.typescriptlang.org/tsconfig)
- 일일이 `tsc`를 사용하지 않고 webpack, gulp같은 빌드 도구를 사용한다.