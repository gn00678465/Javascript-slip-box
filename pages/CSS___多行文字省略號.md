category:: Programing
type:: #CSS
alias:: CSS - 多行文字省略號

- > 透過 `-webkit-line-clamp` 這個屬性來限制區塊容器中內容為指定行數
  且必須要同時搭配以下條件才會生效
	- display 屬性設定為 `-webkit-box` 或 `-webkit-inline-box` 時
	  logseq.order-list-type:: number
	- `webkit-box-orient` 屬性必須設為 `vertical`
	  logseq.order-list-type:: number
- ```css
  .multiline-ellipsis { 
    display: -webkit-box;
    -webkit-box-orient: vertical;
    -webkit-line-clamp: 5;
    overflow: hidden;
  }
  ```
- ## Reference
	- [-webkit-line-clamp](https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-line-clamp)