category:: Programming
type:: #Javascript, #API
alias:: Window.scrollTo

- > 滾動到指定座標
  可作用於 Window 或是 Element 中
- ## Syntax
	- ```js
	  scrollTo(x-coord, x-coord)
	  scrollTo(scrollOptions)
	  ```
	- **Parameter**
		- `x-coord: number`: 水平方向卷軸座標
		- `x-coord: number`: 垂直方向卷軸座標
		- `scrollOptions: ScrollOptions`
			- ```ts
			  interface ScrollOptions {
			    top?: number;
			    left?: number;
			    behavior?: ScrollBehavior
			  }
			  
			  type ScrollBehavior: "auto" | "smooth" | "instant"
			  ```
			- `top`: 等同於 `y-coord`
			- `left`: 等同於 `x-coord`
			- `behavior`:
				- `auto`: 瀏覽器 default
				- `smooth`: 平滑滾動
				- `instant`: 瞬間滾動
	- **Return**
		- `undefined`