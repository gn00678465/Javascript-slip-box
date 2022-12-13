- ## Typescript - `InstanceType<Type>`
	- ```typescript
	  import Component from './Component.vue';
	  
	  type ComponentType = InstanceType<typeof Component>["$props"];
	  ```
- ## Reference
	- [InstanceType](https://www.typescriptlang.org/docs/handbook/utility-types.html#instancetypetype)
	- [Extracting the prop types of a component in Vue 3 (typescript)](https://stackoverflow.com/questions/68602712/extracting-the-prop-types-of-a-component-in-vue-3-typescript-to-use-them-somew)