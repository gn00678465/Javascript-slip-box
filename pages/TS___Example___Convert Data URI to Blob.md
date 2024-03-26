category:: Programming
type:: #Typescript, #Example
alias:: Convert Data URI to Blob

- 將 dataURL 轉成 blob
- 可作為參數帶入 [[URL.createObjectURL]]
- ## Example
	- ```ts
	  function dataURItoBlob(dataURI?: string): Blob | undefined {
	      if (!dataURI) return undefined;
	      const mime = dataURI.split(",")[0].split(":")[1].split(";")[0];
	  
	      const binary =
	        dataURI.split(",")[0].indexOf("base64") >= 0
	          ? window.atob(dataURI.split(",")[1])
	          : decodeURI(dataURI.split(",")[1]);
	      const array = new Uint8Array(binary.length);
	      for (let i = 0; i < binary.length; i++) {
	        array[i] = binary.charCodeAt(i);
	      }
	      return new Blob([array], { type: mime });
	    }
	  ```