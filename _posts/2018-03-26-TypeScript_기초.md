---
title:  "Typescript Fundamentals #02"
date:   2018-03-26 17:00:00
categories: text
---

## Types, Variables, and Function Techniques

#### Type checked
```js
var list: number[] = [1,2,3,4,5];
list =  [10,11,12,13,14,15];

//'string[]' 형식은 'number[]' 형식에 할당할 수 없습니다.  'string' 형식은 'number' 형식에 할당할 수 없습니다.
list = ['A', 'B', 'C', 'D', 'E'];

// Function return types
function numbers(a: number, b:number):string {
  //error log
  return a + b;
  // 'number' 형식은 'string' 형식에 할당할 수 없습니다.
  return (a + b).toString();
}
```
>**_error log_**..
>_list = ['A', 'B', 'C', 'D', 'E'];_
>'string[]' 형식은 'number[]' 형식에 할당할 수 없습니다.  
>'string' 형식은 'number' 형식에 할당할 수 없습니다.

&nbsp;
#### for...in & for...of
```js
// for...in and for...of
var list: string[] = ['apple', 'banana', 'orange'];
for ( var key in list ) {
    var value = list[key];
    console.log(value); //'apple','banana','orange'
}

for ( var key of list ) {
  console.log(key);
}
```

&nbsp;
### Optional parameters
```js
function concatStrings(a: string, b: string, c?: string) {
    return a + b + c;
}

// 선택적임을 나타내는 구문. 이렇게하면 JavaScript 호출 구문을 모방 할 수 있습니다.
// 누락 된 인수가있는 동일한 함수를 호출 할 수 있습니다.
var concat3 = concatStrings("a", "b", "C");
var concat2 = concatStrings("a", "b");
// 2-3개의 인수가 필요한데 1개를 가져왔습니다.
// var concat1 = concatStrings("a");
```
>**_error log_**
> _var concat1 = concatStrings("a");_
> 최소 2개 이상의 인수가 필요함.
> 2-3개의 인수가 필요한데 1개를 가져왔습니다.

&nbsp;
### Function callbacks
```js
var callbackFuntion = function (text) {
    console.log('inside callbcak Function ' + text);
}

function doSomethingWithACallback(initialText, callback) {
    console.log('inside doSomethingWithCallbcak ' + initialText);
    callback(initialText);
}

doSomethingWithACallback('myText', callbackFuntion);
```

&nbsp;
### Union types
```js
// Union types
var unionType: string | number;
unionType = 1;
console.log(unionType);
unionType = 'test';
console.log(unionType);
```

&nbsp;
### Object rest and spread
```js
// Object rest and spread
let firstObj = { id: 1, name: 'firstObj' };
let seconObj = { ...firstObj };

console.log(seconObj.id, seconObj.name);
console.log(firstObj.id, firstObj.name);
```
