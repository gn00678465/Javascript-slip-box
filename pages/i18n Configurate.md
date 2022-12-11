- # 初始化插件
  id:: 6388526c-024c-48c3-9075-9bd30c7175ff
	- ```typescript
	  // src/plugins/i18n/index.ts
	  import { App } from 'vue';
	  import { createI18n } from 'vue-i18n';
	  import zhTW from '../../locales/zh-TW.json';
	  import enUS from '../../locales/en-US.json';
	  
	  type MessageSchema = typeof zhTW
	  
	  export function setupI18n(app: App) {
	    const i18n = createI18n<[MessageSchema], 'zh-TW' | 'en-US'>({
	      legacy: false,
	      locale: 'zh-TW',
	      fallbackLocale: 'zh-TW',
	      globalInjection: false,
	      messages: {
	        'zh-TW': zhTW,
	        'en-US': enUS
	      }
	    });
	  
	    app.use(i18n);
	  }
	  ```
	- **legacy**: 要把 legacy 設為 false，才可以使用 Composition API
	  id:: 638851b8-0ccd-4d6e-b7d0-bdbb7536bb2e
- # 建立語言檔
  id:: 638851ca-99bb-4eab-b21e-ef8d9f8227bd
  collapsed:: true
	- 語系檔支援以下格式
		- json (default)
		  id:: aa2b98be-f321-4cd5-b5b6-3446ad295cec
		- yaml
		- yml
		- json5
	- 於 `src/scales` 資料夾下新增語言檔
	- `es-US.json`
		- ```json
		  {
		    "title": "Title"
		  }
		  ```
	- `zh-TW.json`
		- ```json
		  {
		    "title": "標題"
		  }
		  ```
- # 引入 `Vue-i18n`
  id:: 638853a5-4554-43d8-a65b-f32b89e0d137
	- ```ts
	  // main.ts
	  import { setupI18n } from './plugins';
	  
	  setupI18n(app);
	  ```