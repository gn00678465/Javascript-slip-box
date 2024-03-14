category:: Programming
type:: #Typescript, #Classes
alias:: TS - Classes - Abstract

- abstract 用於定義抽象類別和其中的抽象方法
  logseq.order-list-type:: number
- abstract 不允許被實例化
  logseq.order-list-type:: number
	- ```ts
	  abstract class AbstractObservable {
	    abstract subcribe(o: Observer): void;
	    abstract unsubcribe(o: Observer): void;
	  }
	    
	  const observer = new AbstractObservable();
	  // Cannot create an instance of an abstract class.
	  ```
- abstract 必須被子類別實現
  logseq.order-list-type:: number
	- ```ts
	  class Observer {}
	  
	  abstract class AbstractObservable {
	    abstract subcribe(o: Observer): void;
	    abstract unsubcribe(o: Observer): void;
	  }
	    
	  class Observable extends AbstractObservable {
	    private observers: Observer[]
	  
	    constructor() {
	      super();
	      this.observers = [];
	    }
	  
	    subcribe(o: Observer) {
	      this.observers.push(o)
	    }
	  
	    unsubcribe(o: Observer) {
	      const idx = this.observers.indexOf(o);
	      if (idx !== -1) {
	          this.observers.splice(idx, 1);
	      }
	    }
	  }
	  
	  const observable = new Observable();
	  ```