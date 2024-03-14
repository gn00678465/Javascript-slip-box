category:: Programming
type:: #Typescript
alias:: Access Modifiers - public

- 要存取 class 裡的屬性，必須 `new` 一個 instance ，否則就算將屬性設置為 public ，也無法直接從 class 存取到屬性。
- ```ts
  class Person {
    public name: string;
    age: number;
    constructor(name: string, age: number) {
      this.name = name;
      this.age = age;
    }
  }
  
  const PersonInstance = new Person('Joe', 18);
  
  console.log(Person.name);
  console.log(PersonInstance.name); // Joe
  
  console.log(Person.name);
  console.log(PersonInstance.age); // 18
  ```
- **簡化寫法**
- ```ts
  class Person {
    constructor(public name: string, public age: number) {
    }
  }
  ```