category:: Note
type:: #Note
alias:: IPv4 Address 驗證合法性

- ## Regular Expression
	- ```plain
	  ^(1\d{2}|2[0-4]\d|25[0-5]|[1-9]\d|[1-9])\.(1\d{2}|2[0-4]\d|25[0-5]|[1-9]\d|\d)\.(1\d{2}|2[0-4]\d|25[0-5]|[1-9]\d|\d)\.(1\d{2}|2[0-4]\d|25[0-5]|[1-9]\d|\d)$
	  ```
	- `1\d{2}`: 代表 100 ~ 199 的數字
	- `2[0-4]\d`: 表 200 ~ 240 的數字
	- `25[0-5]`: 表 250 ~ 255
	- `[1-9]\d`: 表 10 ~ 99
	- `[1-9]`: 表 1 ~ 9
- ## 字串拆分方式
	- 以 `.` 分割, 判斷 length 為 4
	  logseq.order-list-type:: number
	- 各自的數字**大於 0 小等於 255**
	  logseq.order-list-type:: number
	- ```ts
	  function isValidIP(ipAddress: string): boolean {
	    const ipBlocks = ipAddress.split('.');
	    if (ipBlocks.length !== 4) return false;
	    for(const ipBlock of ipBlocks) {
	      if (parseFloat(ipBlock) < 0 || parseFloat(ipBlock) > 255) {
	        return false;
	      }
	    }
	    return true;
	  };
	  ```