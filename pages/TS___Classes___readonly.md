category:: Programming
type:: #Typescript, #Classes
alias:: TS - Classes - readonly

- **readonly** 的屬性只能存取不能修改
- ```ts
  class Employee {
    readonly code: string;
    name: string;
    constructor(code: string, name: string)     {
        this.code = code;
        this.name = name;
    }
  }
  
  const employee = new Employee('AA001', 'Joe');
  employee.code = 'AA002';
  // Cannot assign to 'code' because it is a read-only property.
  ```