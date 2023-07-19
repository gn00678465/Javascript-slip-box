category:: Programing
type:: #Javascript, #API
alias:: Window.scrollBy

- > 相對於當前座標滾動多少距離
  可作用於 Window 或是 Element 中
- ## Syntax
	- ```js
	  scrollBy(x-coord, x-coord)
	  scrollBy(scrollOptions)
	  ```
	- **Parameters**
		- `x-coord: number`: 水平方向滾動的距離
		- `x-coord: number`: 垂直方向滾動的距離
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