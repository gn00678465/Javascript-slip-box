category:: Programing

- ## Vue 2
- type:: #Vue2
  version:: 2.6+
	- > Vue2 版本中分為 slots 與 scopedSlots
	- ```vue
	  <!-- slots -->
	  <template v-for="(_, slotName) in $slots" v-slot:[slotName]>
	    <slot :name="slotName" />
	  </template>
	  ```
	- ```vue
	  <!-- scoped slots -->
	  <template v-for="(_, scopedSlotName) in $scopedSlots" v-slot:[scopedSlotName]="slotData">
	    <slot :name="scopedSlotName" v-bind="slotData" />
	  </template>
	  ```
- ## Vue 3
- category:: Note
  type:: #Vue3
  version:: 3.x+
	- ```vue
	  <template v-for="(_, slot) in $slots" v-slot:[slot]="scope">
	      <slot :name="slot" v-bind="scope || {}" />
	  </template>
	  ```
- ## Reference
	- [Vue - how to pass down slots inside wrapper component?](https://stackoverflow.com/questions/50891858/vue-how-to-pass-down-slots-inside-wrapper-component)