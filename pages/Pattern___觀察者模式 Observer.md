category:: Programming
type:: #Pattern
alias:: 觀察者模式 Observer

- > 定義了一種一對多的依賴關係，讓多個 Observer (觀察者)物件同時監聽某一個 Observable (可觀察)物件，當此 Observable 狀態發生變化，會通知所有 Observer 。
- ## Observer Pattern 實作流程
- ### 設計 Observer 的 Interface
	- ```typescript
	  interface Observer {
	    update(temperature: number, humidity: number, pressure: number): void
	  }
	  ```
- ### 設計 Observable 的 Interface
	- ```typescript
	  interface Observable {
	    subcribe(o: Observer): void;
	    unsubcribe(o: Observer): void;
	    notifyObservers(temperature: number, humidity: number, pressure: number): void;
	  }
	  ```
- ### 實做 Observable
	- ```typescript
	  class WeatherStation implements Observable {
	    private observers: Observer[];
	    constructor() {
	      this.observers = [];
	    }
	  
	    public subcribe(o: Observer) {
	      this.observers.push(o);
	    }
	  
	    public unsubcribe(o: Observer) {
	      const idx = this.observers.indexOf(o);
	      if (idx !== -1) {
	          this.observers.splice(idx, 1);
	      }
	    }
	  
	    public notifyObservers(temperature: number, humidity: number, pressure: number) {
	      this.observers.forEach((observer) => {
	          observer.update(temperature, humidity, pressure);
	      })
	    }
	  }
	  ```
- ### 實做 Observer
	- ```typescript
	  class WeatherApp implements Observer {
	      update(temperature: number, humidity: number, pressure: number) {
	          console.log(`The temperature is ${temperature}°C`);
	          console.log(`The humidity is ${humidity}%`);
	          console.log(`The pressure is ${pressure}Pa`);
	      }
	  }
	  ```
- ### 實際應用
	- ```typescript
	  // 實例化 Observable
	  const station = new WeatherStation();
	  // 實例化 Observer
	  const app1 = new WeatherApp();
	  const app2 = new WeatherApp();
	  // 訂閱
	  station.subcribe(app1);
	  station.subcribe(app2);
	  // 通知
	  station.notifyObservers(30, 50, 1000);
	  // 取消訂閱
	  station.unsubcribe(app2);
	  ```
- ## Reference
	- [觀察者模式（ Observer Pattern ） feat. TypeScript](https://medium.com/enjoy-life-enjoy-coding/design-pattern-%E5%8F%AA%E8%A6%81%E4%BD%A0%E6%83%B3%E7%9F%A5%E9%81%93-%E6%88%91%E5%B0%B1%E5%91%8A%E8%A8%B4%E4%BD%A0-%E8%A7%80%E5%AF%9F%E8%80%85%E6%A8%A1%E5%BC%8F-observer-pattern-feat-typescript-8c15dcb21622)
	- [javascript 设计模式之观察者模式](https://juejin.cn/post/6961017766560137230)