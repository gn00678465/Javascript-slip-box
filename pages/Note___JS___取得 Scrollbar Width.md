category:: Note
type:: #Javascript, #Note
alias:: JS - 取得 Scrollbar Width

- Use `Window.innerWidth` to get the interior width of the window.
  logseq.order-list-type:: number
- Use `Element.clientWidth` to get the inner width of the [`Document`](https://developer.mozilla.org/en-US/docs/Web/API/Document) element.
  logseq.order-list-type:: number
- Subtract the two values to get the width of the vertical scrollbar.
  logseq.order-list-type:: number
- ```ts
  const getScrollbarWidth = () =>  window.innerWidth - document.documentElement.clientWidth;
  ```
- ## Reference
	- [Scrollbar Width](https://www.30secondsofcode.org/js/s/get-scrollbar-width/)