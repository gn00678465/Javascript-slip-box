category:: Programing
type:: Pattern
alias:: 狀態模式 State

- > **State** is a behavioral design pattern that lets an object alter its behavior when its internal state changes. It appears as if the object changed its class.
  允許一個物件在其內部狀態改變時改變它的行為。這個物件看起來似乎修改了它的類別。
- 原則：在狀態模式中，關鍵在於將每種狀態封裝成單獨的類別，跟狀態相關的行為一併封裝在類別的內部。
- ## Example
	- ```javascript
	  class State {
	      constructor(context) {
	          this.color = '';
	          this.context = context;
	      }
	  
	      handleStateChange() {
	          throw new Error('nextState method is required!!')
	      }
	  }
	  // 紅燈狀態與其行為
	  class RedLightState extends State {
	      constructor(context) {
	          super(context);
	          this.color = 'red';
	      }
	  
	      handleStateChange() {
	          console.log('綠燈');
	          this.context.setState(this.context.greenLight);
	      }
	  }
	  // 綠燈狀態與其行為
	  class GreenLightState extends State {
	      constructor(context) {
	          super(context);
	          this.color = 'green';
	      }
	  
	      handleStateChange() {
	          console.log('黃燈');
	          this.context.setState(this.context.yellowLight);
	      }
	  }
	  // 黃燈狀態與其行為
	  class YellowLightState extends State {
	      constructor(context) {
	          super(context);
	          this.color = 'yellow';
	      }
	  
	      handleStateChange() {
	          console.log('紅燈');
	          this.context.setState(this.context.redLight);
	      }
	  }
	  
	  class Light {
	      constructor() {
	          this.redLight = new RedLightState(this);
	          this.greenLight = new GreenLightState(this);
	          this.yellowLight = new YellowLightState(this);
	  
	          this.state = this.redLight;
	      }
	  
	      get currentState() {
	          return this.state.color
	      }
	  
	      nextState() {
	          this.state.handleStateChange()
	      }
	  
	      setState(newState) {
	          this.state = newState;
	      }
	  }
	  
	  const light = new Light();
	  
	  light.nextState(); // 綠燈
	  light.currentState // green
	  ```
- ## Refernece
	- [State](https://refactoring.guru/design-patterns/state)
	- [javascript 设计模式之状态模式](https://juejin.cn/post/6963552093777068046)