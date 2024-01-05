category:: Note
type:: #Javascript
alias:: JS - 判斷手機瀏覽器的方式

- ## navigator.userAgent
	- > 分析 user agent 是否包含手機的關鍵字
	- ```ts
	  function isMobileDevice(): Boolean {
	    const mobileDevices = ['Android', 'webOS', 'iPhone', 'iPad', 'iPod', 'BlackBerry', 'Windows Phone'];
	    return mobileDevices.some((device) => navigator.userAgent.match(new RegExp(device, 'i')));
	  }
	  ```
- ## window.screen, window.innerWidth
	- > 透過判斷螢幕寬度
-
- ## Reference
	- [JavaScript 侦测手机浏览器的五种方法](https://www.ruanyifeng.com/blog/2021/09/detecting-mobile-browser.html)