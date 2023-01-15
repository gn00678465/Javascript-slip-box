category:: Programing
type:: Javascript, API
alias:: IntersectionObserver

- ```javascript
  const observer = new IntersectionObserver(callback, options);
  ```
- **params**
	- `callback: (IntersectionObserverEntry[]) => viod`
	- options:
		- `root: HTMLElement | null`:
		- `rootMargin: string`:
		- `threshold: number`:
- **Methods**
	- `observer(target: HTMLElement)`:
	- `disconnect()`:
	- `unobserve(target: HTMLElement)`:
	- `takeRecords()`:
- ## Reference
	- [Intersection Observer API - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)
	- [IntersectionObserverEntry](https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry)