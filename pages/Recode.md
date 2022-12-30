Typescript:: Record
title:: Recode

- ## Record<Keys, Type>
	- ```typescript
	  interface PageInfo {
	    title: string;
	  }
	  
	  type Page = "home" | "about" | "contact";
	  
	  // Mapped Types
	  type ToNavType = {
	    [P in Page]: PageInfo;
	  };
	  ```
	- ```typescript
	  type ToNavType<T extends keyof any> = {
	    [P in T]: PageInfo;
	  };
	  ```
	- ```typescript
	  type ToNavType<T extends keyof any, K> = {
	    [P in T]: K;
	  };
	  
	  type NavType = ToNavType<Page, PageInfo>;
	  type NaveType = Record<Page, PageInfo>;
	  ```
- ## Reference
	- [Utility Types - Record](https://www.typescriptlang.org/docs/handbook/utility-types.html#recordkeys-type)
	- [[Day17] TS：理解 Pick、Record 的實作]([https://pjchender.dev/ironman-2021/ironman-2021-day17/](https://pjchender.dev/ironman-2021/ironman-2021-day17/#record))