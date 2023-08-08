category:: Note
type:: #CSS
alias:: CSS - 單行文字省略號

- > 省略號就是「…」，又稱刪節號
- ```css
  .text-ellipsis {
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
  }
  ```
	- `white-space: nowrap`: 強制讓文字不換行
	- `overflow: hidden`: 隱藏此行文字超出容器的部分
	- `text-overflow: ellipsis`: 為溢出的文字加上省略號即可