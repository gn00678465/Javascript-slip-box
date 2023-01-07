category:: Programing
type:: Axios
alias:: 取消請求

- 從 `v0.22.0` 後採用 [`AbortController`](https://developer.mozilla.org/en-US/docs/Web/API/AbortController) 作為取消請求的 API
- 與 Vanllia JS 的 `Fetch` 為相同的取消請求 API
- 舊的取消請求 API  `CancelToken` 預計廢棄
- ## useage
	- ```javascript
	  const controller = new AbortController();
	  
	  axios.get('/api', {
	    single: controller.single
	  }).then((response) => {
	  	// do...
	  });
	  
	  // abort request
	  controller.abort();
	  ```
-
- ## Reference
	- [取消所有的 api 請求，使用 axios 搭配 AbortController signal API](https://muki.tw/tech/vue/vue-axios-cancel-api-request-abortcontroller-signal/)