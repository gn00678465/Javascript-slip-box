category:: Note
type:: #note, #Bitwise
alias:: Bitwise - Operator

- ## AND `&`
- > & 可以判斷位元是不是 1
	- 0 & 0 = 0
	  logseq.order-list-type:: number
	- 0 & 1 = 0
	  logseq.order-list-type:: number
	- 1 & 0 = 0
	  logseq.order-list-type:: number
	- 1 & 1 = 1
	  logseq.order-list-type:: number
	- ```plain
	    0111 0100  -> 116
	  & 0010 1001  -> 41
	  -----------
	    0010 0000  -> 32
	  ```
- ## OR `|`
- > | 可以把位元強制標記成 1
	- 0 | 0 = 0
	  logseq.order-list-type:: number
	- 0 | 1 = 1
	  logseq.order-list-type:: number
	- 1 | 0 = 1
	  logseq.order-list-type:: number
	- 1 | 1 = 1
	  logseq.order-list-type:: number
	- ```plain
	    0111 0100  -> 116
	  & 0010 1001  -> 41
	  -----------
	    0111 1101  -> 125
	  ```
- ## NOT `~`
- > 顛倒一個變數的每個位元的 0 和 1
	- ~0 = 1
	  logseq.order-list-type:: number
	- ~1 = 0
	  logseq.order-list-type:: number
	- ```plain
	  ~ 00000000000000000000000000000011   -> 3
	  ----------------------------------
	    11111111111111111111111111111100   -> -4
	  ```
- > & 和 ~ 可以把位元強制標記成 0
- ## XOR `^`
- > 可以顛倒位元的 0 和 1
	- 0 ^ 0 = 0
	  logseq.order-list-type:: number
	- 0 ^ 1 = 1
	  logseq.order-list-type:: number
	- 1 ^ 0 = 1
	  logseq.order-list-type:: number
	- 1 ^ 1 = 0
	  logseq.order-list-type:: number
	- ```plain
	    0000 0000 0000 0000 0000 0000 0111 0100   -> 116
	  ^ 0000 0000 0000 0000 0000 0000 0010 1001   -> 41
	  -----------------------------------------
	    0000 0000 0000 0000 0000 0000 0101 1101   -> 93
	  ```