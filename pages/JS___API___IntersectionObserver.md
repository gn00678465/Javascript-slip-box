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
	- `unobserve(target: HTMLElement)`:
	- `disconnect()`:
	- `takeRecords()`:
- ## Reference
	- [Intersection Observer API - MDN Web Docs](https://developer.mozilla.org/en-US/docs/Web/API/Intersection_Observer_API)
	- [IntersectionObserverEntry](https://developer.mozilla.org/en-US/docs/Web/API/IntersectionObserverEntry)