category:: Note
type:: #Axios, #Note
alias:: Axios - Setting dynamic baseURL

- > 動態設定 Axios 的 baseurl
  使用 interceptor 實現
- ```js
  axiosInstance.interceptors.request.use((config) => {
    config.baseURL= newBaseURL;
    return config;
  }, (error) => Promise.reject(error))
  ```