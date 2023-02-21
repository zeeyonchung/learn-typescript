# TS 모듈시스템
```
// types.ts
export interface Todo {
    title: string;
    checked: boolean;
}
```
```
// app.ts
import { Todo } from './types.ts'

let item: Todo = {
    title: '할 일 1',
    checked: false,
};
```