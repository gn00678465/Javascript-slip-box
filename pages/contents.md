- <p style="font-size: 20px; font-weight: bold; color: #333;">Git</p>
	- 📚 [[Git 常用指令]]
- <p style="font-size: 20px; font-weight: bold; color: #333;">GitHub</p>
	- [[GitHub Actions]]
- <p style="font-size: 20px; font-weight: bold; color: #f7df1e;">JavaScript</p>
- <p style="font-size: 20px; font-weight: bold; color: #3178c6;">TypeScript</p>
	- **Basic**
	  collapsed:: true
		- query-table:: true
		  query-properties:: [:page :category :type :alias :version]
	- **Utility**
	  query-table:: true
	  query-properties:: [:page :category :type :alias]
	  collapsed:: true
		- {{query (and (property :type "#Typescript") (property :type "#Utility"))}}
		  query-properties:: [:page :category :type :alias :version]
		  query-table:: true
- <p style="font-size: 20px; font-weight: bold; color: #61DBFB">React</p>
	- 📚 [[React 學習筆記]]
	- **Hooks**
	  collapsed:: true
		- {{query (and (property :type "#React") (property :type "#Hooks") (not (property :type "#ReactRouter")))}}
		  query-table:: true
		  query-properties:: [:page :category :type :alias]
	- **APIs**
	  collapsed:: true
		- {{query (and (property :type "#React") (property :type "#API"))}}
		  query-sort-by:: alias
		  query-table:: true
		  query-sort-desc:: false
		  query-properties:: [:page :category :type :alias]
	- 📓 **Note**
	  collapsed:: true
		- [[React 宣告帶有 childrend 的 props]]
		- [[React - Batch Update]]
- <p style="font-size: 20px; font-weight: bold; color: #42b883;">Vue.js</p>
- <p style="font-size: 20px; font-weight: bold; color: #0db7ed;">Docker</p>
  collapsed:: true
	- {{query (property :type "#Docker")}}
	  query-table:: true
	  query-properties:: [:page :category :type :alias]