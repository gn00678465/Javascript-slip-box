category:: Note
type:: #Typescript
alias:: Discriminated Unions 範例

- [[Discriminated Unions]] 說明
- ```ts
  type SuccessResponse = {
      status: 'Success'
  }
  
  type SuccessResponseWithData<T> = {
      status: 'Success';
      data: T
  }
  
  type FailureResponse = {
      status: 'Error';
      message: string;
  }
  
  type ResponseUnioType<T = undefined> = (T extends undefined ? SuccessResponse : SuccessResponseWithData<T>) | FailureResponse;
  ```