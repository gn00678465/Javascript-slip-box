category:: Programing
type:: Vue, Typescript
alias:: 提取 Vue3 Component props 的 type
version:: 3.x+

- ## Typescript - `InstanceType<Type>`
	- ```typescript
	  import Component from './Component.vue';
	  
	  type ComponentType = InstanceType<typeof Component>["$props"];
	  ```
- ## Reference
	- [InstanceType](https://www.typescriptlang.org/docs/handbook/utility-types.html#instancetypetype)
	- [Extracting the prop types of a component in Vue 3 (typescript)](https://stackoverflow.com/questions/68602712/extracting-the-prop-types-of-a-component-in-vue-3-typescript-to-use-them-somew)