---
title:  "Typescript Fundamentals #01"
date:   2018-03-20 14:00:00
categories: text
---

# TypeScript

#### Installing TypeScript

For NPM users:
```Bash
npm install -g typescript
```

#### tsconfig.json

```json
{
  "include": ["./src/ts"],
  "compilerOptions":{
    "target":"es6",
    "module":"commonjs",
    "baseUrl":"./src/ts/",
    "outDir":"./dist/js/"
  }
}
```
`tsconfig.json` 이 없어도 빌드하는 데 문제는 없지만, 컴파일할 때마다 다양한 옵션을 반복적으로 지정하는 것은 번거로우니 사용하는 것이 좋다.


[Reference tsconfig.json](http://www.typescriptlang.org/docs/handbook/tsconfig-json.html)

#### CLI Build
```Bash
tsc test.ts
```
#### VSCODE Build
```Bash
tsc test.ts or ctrl + shift + b
```
`localhost:8000/src/index.html`
vscode에서 `ctrl + shift + b`을 사용해 빌드하면
`Starting compilation in watch mode...` 메시지가 뜨고 `liveReload` 기능이 실행된다. 개발시에는 코드가 빈번히 변경되므로 코드의 변경을 감시하도록 한다.

#### Example TypeScript compile JS
**TypeScript code**
```js
interface Person {
    firstName: string;
    lastName: string;
}
function greeter(person: Person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}
let user = { firstName: 'Jane', lastName: 'User' };
document.body.innerHTML = greeter(user);
```
```Bash
tsc greeter.ts
```

**Compile js code**
```js
function greeter(person) {
    return "Hello, " + person.firstName + " " + person.lastName;
}
var user = { firstName: 'Jane', lastName: 'User' };
document.body.innerHTML = greeter(user);
```
