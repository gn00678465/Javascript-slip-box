category:: Programing
type:: #Typescript
alias:: implements

- > implements (實踐)通常用在實踐抽象的 Interface (介面)的所有方法和屬性。
- **class 中必須包含所有 interface 定義的屬性和方法**
- ```typescript
  interface Shape {
    getArea: () => number;
  }
  
  class Circle implements Shape {
    private radius: number;
    constructor(radius: number) {
      this.radius = radius;
    }
  
    public getArea() {
      return Math.PI * this.radius ** 2;
    }
  }
  
  class Square implements Shape {
    private width: number;
    private height: number;
    constructor(width: number, height: number) {
      this.width = width;
      this.height = height;
    }
  
    public getArea() {
      return this.width * this.height;
    }
  }
  ```
- **可以實踐多個 interface**
- > 每個 interface 用逗號分隔
- ```typescript
  interface Shape {
    getArea: () => number;
  }
  
  interface Volume {
    getVolume: () => number;
  }
  
  class Cylinder implements Shape, Volume {
    private radius: number;
    private height: number;
    constructor(radius: number, height: number) {
      this.radius = radius;
      this.height = height;
    }
  
    public getArea() {
      return Math.PI * this.radius ** 2;
    }
  
    public getVolume() {
      return this.getArea() * this.height
    }
  }
  ```
-
- ## Reference
	- [TypeScript 類別繼承(Class Inheritance) v.s. 實踐(Implements)](https://ithelp.ithome.com.tw/articles/10225777)