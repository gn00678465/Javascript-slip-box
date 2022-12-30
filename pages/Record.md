Typescript:: Record

- ```typescript
  interface PageInfo {
    title: string;
  }
  
  type Page = "home" | "about" | "contact";
  
  // Mapped Types
  type NavType = {
    [P in Page]: PageInfo
  }
  ```
- ```typescript
  type NavType<T extends Page> = {
    [P in T]: PageInfo
  }
  ```