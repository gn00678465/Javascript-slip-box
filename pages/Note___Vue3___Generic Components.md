category:: Note
type:: #Vue3, #Typescript
alias:: Vue3- Generic Components
version:: 3.3+

- > 使用 Vue3 的 `<script setup>` component 可以透過 `generic` 新增的屬性設定泛型的型別(generic type)
	- ```vue
	  <script setup lang="ts" generic="T">
	  const props = defineProps<{
	    data: T[]
	  }>()
	  </script>
	  ```
- **使用方式與 Typescript 相同，可以使用 `extends` 限制型別**
	- ```vue
	  <script setup lang="ts" generic="T extends string & {}, U extends Item">
	  import type { Item } from './types'
	  const props = defineProps<{
	    name: T;
	    list: U[];
	  }>()
	  </script>
	  ```
- ## Reference
	- [Announcing Vue 3.3](https://blog.vuejs.org/posts/vue-3-3#script-setup-typescript-dx-improvements)