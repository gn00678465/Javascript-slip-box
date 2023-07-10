category:: Programing
type:: #Typescript
alias:: Type Guard

- > Type Guards allow you to narrow down the type of an object within a conditional block.
  > 將 type 限制成更小範圍的 type 的行為
- ### typeof
- > 使用  if 判斷當 value 的 type 為 string 才會執行
  > 判斷的語法稱之為 **Type Guard**
- ```typescript
  function isString(value: string | undefined) {
    if (typeof value === 'string') {
      return value.substr(1)
    }
  }
  ```
- ### instanceof
- ```typescript
  class Cat {
    name = 'cat';
  }
  class Dog {
    name = 'dog'
  }
  function doStuff(animal: Cat | Dog) {
    if (animal instanceof Cat) {
      // animal: Cat
    }
    if (animal instanceof Dog) {
      // animal: Dog
    }
  }
  ```
- ### in
- > 使用 `in` 判斷某一個屬性在特定的 object 或其原型鏈中
- ```typescript
  interface A {
    x: number;
  }
  interface B {
    y: string
  }
  function doStuff(q: A | B) {
    if ('x' in q) {
      // q: A
    }
    else {
      // q: B
    }
  }
  ```
- ### Literal Type Guard
- > 使用 `===` / `==` / `!==` / `!=` 比對文字
- ```typescript
  type Foo = {
    kind: 'foo', // Literal type 
    foo: number
  }
  type Bar = {
    kind: 'bar', // Literal type 
    bar: number
  }
  
  function doStuff(arg: Foo | Bar) {
      if (arg.kind === 'foo') {
          console.log(arg.foo); // arg: Foo
      }
      else {  // MUST BE Bar!
          console.log(arg.bar); // arg: Bar
      }
  }
  ```
- ### User Defined Type Guards
- `:parameterName is TYPE`
- 要定義 user-defined type guard，只需要定義一個函式，其「回傳值」的型別會是 **type predicate**, ex: `value is string`
- ```typescript
  interface Foo {
      foo: number;
      common: string;
  }
  
  interface Bar {
      bar: number;
      common: string;
  }
  
  /**
   * User Defined Type Guard!
   */
  function isFoo(arg: any): arg is Foo {
      return arg.foo !== undefined;
  }
  
  function doStuff(arg: Foo | Bar) {
      if (isFoo(arg)) {
  		// arg: Foo
      }
      else {
  		// arg: Bar
      }
  };
  ```
- ## Reference
	- [Type Guard](https://basarat.gitbook.io/typescript/type-system/typeguard)
	- [[TS] Type Guard and Narrowing](https://pjchender.dev/typescript/ts-narrowing/)