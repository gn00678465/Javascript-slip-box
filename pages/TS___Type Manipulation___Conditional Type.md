category:: Programing
type:: Typescript
alias:: Conditional Type

- ```ts
  type NewType = SomeType extends OtherType ? TrueType : FalseType;
  ```
- background-color:: red
  > 當 **SomeType** 滿足 **OtherType**; **NewType** 為 **TrueType**, 否則為 **FalseType**