category:: Programing
type:: #Typescript, #Utility, #Custom
alias:: PartPartial

- ## `PartPartial<Type, Keys>`
- > 建立自己的 Utility
  > 傳入一個型別 `Type` & 其中幾個 Key `Keys`，回傳一個新的型別，且 `Keys` 必須是 **Optional**
- ### 實做
- ```typescript
  type PartPartial<
    T extends Record<any, any>,
    K extends keyof T
  > = Partial<Pick<T, K>> & Pick<T, Exclude<keyof T, K>>;
  ```
	- 使用 [[Pick]] 取出以 [[Exclude]] 排除 `K` 以外 keys 的型別
	- 使用 [[Partial]] 包含 `K` 的 keys 的型別
	- 將兩者聯集 `&`
- ## Reference