category:: Note
type:: #Javascript
alias:: Download file

- > 使用 HTML 5 中 `a` 新增的屬性 `download` 實現下載功能
- ```ts
  function forceDownload(fileName: string, blobUrl: string) {
    const anchor = document.createElement("a");
    anchor.href = blobUrl;
    anchor.download = fileName;
    document.body.appendChild(anchor);
    anchor.click();
    anchor.remove();
  }
  ```
- **bolbUrl**
	- ```ts
	  const bolbUrl = (data: Bolb) => URL.createObjectURL(data);
	  ```
	- ```ts
	  const bolbUrl = (
	    array: string,
	    format: string
	  ) => URL.createObjectURL(new Blob(data, { type: format }))
	  ```
		- **Parameters**
			- **`array`**: `BlobPart[]`
				- 由 `ArrayBuffer`、`Blob`、`String` 所組成的 Array
			- **`format`**: [MIME Type](https://developer.mozilla.org/zh-TW/docs/Web/HTTP/Basics_of_HTTP/MIME_types)
- ## Reference
	- [BlobPart](https://microsoft.github.io/PowerBI-JavaScript/modules/_node_modules_typedoc_node_modules_typescript_lib_lib_dom_d_.html#blobpart)