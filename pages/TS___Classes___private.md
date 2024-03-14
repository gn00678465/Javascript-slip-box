category:: Programming
type:: #Typescript, #Classes
alias:: TS - Classes - private

- Javascript 要達到此目的需要在屬性前面加上 `#`
  logseq.order-list-type:: number
- 在屬性前面加上 **private** 代表此屬性是 class 私有的，只能於 class 內部才可存取
  logseq.order-list-type:: number
	- 從外部直接存取 class 本體的 private 屬性，或是 `new` 一個 instance 存取 private 屬性都會發生 Error。
- 要從外部存取 private 屬性的方法只能寫一個 **getter** 或是 **function** 來回傳內部的 private 屬性
  logseq.order-list-type:: number
	- getter 只能 new instance 後呼叫，不能直接從 class 本體呼叫
- ```ts
  class Person {
    // 習慣將 private 的屬性加上_，標示為 private
    private _name: string
    private _age: number
    constructor(name: string, age: number) {
      this._age = age;
      this._name = name;
    }
  
    get getAge() {
      return this._age;
    }
  }
  
  const PersonInstance = new Person('Joe', 18);
  
  console.log(Person.getAge);
  // Property 'getAge' does not exist on type 'typeof Person'.
  console.log(PersonInstance.age);
  // Property 'age' does not exist on type 'Person'
  console.log(PersonInstance.getAge); // 18
  ```
- ### private constructor
- > 該類別不允許被繼承或者實例化
- ```ts
  class Count {
    private _count: number
    private constructor(count: number) {
      this._count = count;
    }
  
    get getCount() {
      return this._count;
    }
  }
  
  const PersonInstance = new Count(18);
  // Constructor of class 'Count' is private and only accessible within the class declaration.
  ```