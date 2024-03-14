category:: Programming
type:: #Typescript
alias:: Access Modifiers - protected

- 在屬性前面加上 **protected** 後只能於 class 內部和繼承該 class 的 **繼承的class** 可以存取的到該屬性
  logseq.order-list-type:: number
- 在 **繼承的class** 內部可以直接用 **this.[屬性]** 存取到 **父class** 的 protected 屬性
  logseq.order-list-type:: number
- protected 屬性無法在外部直接從 class 本體或是 instance 存取
  logseq.order-list-type:: number
- ### protected constructor
  
  > 允許在子類別中使用
- ```ts
  type Gender = 'male' | 'female'
  
  class Parent {
    protected gender: Gender
    protected constructor(gender: Gender) {
      this.gender = gender;
    }
  }
  
  class Child extends Parent {
    public name: string;
    public age: number
    constructor(name: string, age: number, gender: Gender) {
      super(gender);
      this.age = age;
      this.name = name;
    }
  
    get getGender(): Gender {
      return this.gender;
    }
  }
  
  const Joe = new Child('Joe', 18, 'male');
  
  console.log(Joe.gender);
  // Property 'gender' is protected and only accessible within class 'Parent' and its subclasses.
  ```