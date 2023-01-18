- > 將 Typescript 自動推導的 Type 建立成一個可以使用的 Type
- ```typescript
  const person = {
    name: 'Doe',
    age: 20
  }
  type PersonType = typeof person;
  // { name: string; age: number }
  ```
- ## 搭配 [[Keyof operator]] 使用
	- ```typescript
	  type PersonKeyTypes = keyof typeof person
	  // name | age
	  ```
- ## Reference
	- [Typeof Type Operator](https://www.typescriptlang.org/docs/handbook/2/typeof-types.html)