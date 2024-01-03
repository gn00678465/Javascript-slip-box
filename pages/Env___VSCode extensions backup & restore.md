category:: Environment
type:: #Env
alias:: VSCode extensions backup & restore

- ## Backup
	- ```sh
	  code --list-extensions >> vs_code_extensions_list.txt
	  ```
- ## Restore
	- **windows**
	- ```powershell
	  code --list-extensions | % { "code --install-extension $_" }
	  ```
	- **Linux**
	- ```bash
	  cat vs_code_extensions_list.txt | xargs -n 1 code --install-extension
	  ```
	- **安裝單一 Extension**
	- ```sh
	  code --install-extension <extension_id>
	  ```
- ## Reference
	- [Settings Sync](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)