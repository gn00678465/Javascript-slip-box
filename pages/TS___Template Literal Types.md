category:: Programing
type:: #Typescript
alias:: Template Literal Types
version:: 4.1+

- # Template Literal Types
- ## 基本使用
	- 基本使用方式與 ES6 中的 [Template literals](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals) 相同
	- ```ts
	  type World = 'world';
	  type TheWorld = `the ${World}`; // the world
	  ```
- ## 搭配 Union
	- > 依據傳入的 Union ，自動組成新的 Union
	- ```ts
	  type InputEvent = 'input' | 'change';
	  type MouseEvent = 'click' | 'dbclick' ;
	  type EventHandler = `on${InputEvent | MouseEvent}`;
	  	// "oninput" | "onchange" | "onclick" | "ondbclick"
	  ```
- ## 將 Enum 的 values 轉成 Union Type
	- ```ts
	  enum EnumEventType {
	    input = 'Input',
	    change =  'Change',
	    click = 'Click'
	  };
	  type EventType = `${EnumEventType}`; // "Input" | "Change" | "Click"
	  ```
- ## [[String manipulation types]]
- ## Reference
	- [Template Literal Types](https://www.typescriptlang.org/docs/handbook/2/template-literal-types.html)