category:: Programing
type:: Typescript, Utility, Custom
alias:: PartRequired

- ## `PartRequired<Type, Keys>`
- > 建立自己的 Utility
  > 傳入一個型別 `Type` & 其中幾個 Key `Keys`，回傳一個新的型別，且 `Keys` 必須是 **Required**
- ### 實做
- ```typescript
  type PartRequired<
    T extends Record<any, any>,
    K extends keyof T
  > = Required<Pick<T, K>> & Partial<Pick<T, Exclude<keyof T, K>>>
  ```
	- 使用 [[Pick]] 取出以 [[Exclude]] 排除 `K` 以外 keys 的型別
	- 使用 [[Required]] 包含 `K` 的 keys 的型別
	- 將兩者聯集 `&`
## Reference