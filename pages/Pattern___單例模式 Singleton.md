category:: Programming
type:: #Pattern
alias:: 單例模式 Singleton

- > 保證一個類別只有一個實例，並提供一個存取該實例的全域節點
  如使用此類別建立多個實例，仍指向同一個實例
- ```ts
  class Singleton {
    private static instance: Singleton;
    
    private constructor() {
      // Private constructor to prevent direct instantiation
    }
    
    public static getInstance(): Singleton {
      if (!Singleton.instance) {
        Singleton.instance = new Singleton;
      }
      return Singleton.instance;
    }
  }
  
  // usage
  const singleton1 = Singleton.getInstance();
  const singleton2 = Singleton.getInstance();
  
  console.log(singleton1 === singleton2); // true
  ```
- **Example**
- ```ts
  enum LogLevel {
    INFO,
    ERROR,
    WARNING
  }
  
  class Logger {
    private static instance: Logger;
    
    private constructor() {}
    
    public static getInstance(): Logger {
      if (!Logger.instance) {
        Logger.instance = new Logger;
      }
      return Logger.instance;
    }
    
    public log(level: LogLevel, message: string): void {
      // Log the message with the specified level
      console.log(`[${LogLevel[level]}] ${message}`);
    }
  }
  
  const logger1 = Logger.getInstance();
  logger1.log(LogLevel.INFO, "Application started");
  
  const logger2 = Logger.getInstance();
  logger2.log(LogLevel.ERROR, "An error occurred");
  
  console.log(logger1 === logger2); // true
  ```
- ## Reference
	- [Singleton Pattern](https://www.patterns.dev/vanilla/singleton-pattern)
	- [Singleton in Typescript](https://refactoring.guru/design-patterns/singleton/typescript/example)
	- [初探 Singleton Pattern 設計模式](https://muki.tw/introduction-singleton-design-pattern/)