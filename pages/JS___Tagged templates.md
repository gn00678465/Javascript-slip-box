category:: Programing
type:: #Javascript, #ES6
alias:: Tagged templates

- > Template literals 的進階用法
- ## Syntax
	- > 直接於 function 後面使用 template literal
	  1. 先將 template literal 的內容切成多個參數
	  2. 呼叫函式並帶入上面的參數
	- ```js
	  console.log('Hello world'); // Hello world
	  console.log`Hello world`; // ['Hello world', raw: Array(1)]
	  ```
	- **使用 template literals 的變數 `${}`**
	- ```js
	  let name = 'abc';
	  
	  function print(template) {
	    console.log('template', template);
	    console.log('arguments', arguments);
	  };
	  
	  print`Hello ${name} world`;
	  // template ['Hello ', ' world', raw: Array(2)]
	  // arguments [['Hello ', ' world'], 'abc']
	  ```
	- **搭配 spread operator & rest operator**
	- ```js
	  let name = 'Dio';
	  let skill = 'The world';
	  
	  function tag(template, ...parameters) {
	    console.log(template);
	    console.log(parameters);
	  };
	  
	  tag`<p>${name}: ${skill}</p>`;
	  // ['<p>', ': ', '</p>', raw: Array(3)]
	  // ['Dio', 'The world']
	  ```
- ## Referende
	- [tagged templates](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals#tagged_templates)
	- [[筆記] JavaScript ES6 中的模版字符串（template literals）和標籤模版（tagged template）](https://pjchender.blogspot.com/2017/01/javascript-es6-template-literalstagged.html)