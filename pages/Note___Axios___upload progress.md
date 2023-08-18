category:: Note
type:: #Axios
alias:: axios - upload progress

- ```ts
  const onUploadProgress = (progressEvent: ProgressEvent) => {
    const { loaded, total, lengthComputable } = progressEvent;
    const percent = Math.floor((loaded * 100) / total);
    // 
  }
  ```
	- **Params**
		- **`progressEvent`**: `ProgressEvent`
			- **`lengthComputable`**: `Boolean`
				- 是否已知傳輸的總大小
			- **`loaded`**: `number`
				- 自作業開始時傳輸的位元組數目。 這不包括標頭和其他額外負荷，但只包含內容本身。
			- **`total`**: `number`
				- 作業期間將傳輸的內容位元組總數。 如果總大小未知，則此值為零
- ```js
  function upload() {
    return axios.post(url, formData, {
      onUploadProgress
    })
  }
  ```
- ## Reference
	- [Add upload progress to axios request](https://thecodersblog.com/add-upload-progress-axios-request)