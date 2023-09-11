- <p style="font-size: 20px; font-weight: bold; color: #333;">Git</p>
	- 📚 [[Git 常用指令]]
	- 📓 **Note**
	  collapsed:: true
		- [[Git commit 的 type]]
		- [[約定式提交 Conventional Commits]]
- <p style="font-size: 20px; font-weight: bold; color: #333;">GitHub</p>
	- [[GitHub Actions]]
- <p style="font-size: 20px; font-weight: bold; color: #f7df1e;">JavaScript</p>
- <p style="font-size: 20px; font-weight: bold; color: #3178c6;">TypeScript</p>
	- **Basic**
	  collapsed:: true
		- {{query (and (property :type "#Typescript") (not (property :type "#Utility")) (not (property :type "#React")) (not (property :type "#Vue3")) )}}
		  query-table:: true
		  query-properties:: [:page :category :type :alias :version]
	- **Utility**
	  query-table:: true
	  query-properties:: [:page :category :type :alias]
	  collapsed:: true
		- {{query (and (property :type "#Typescript") (property :type "#Utility"))}}
		  query-properties:: [:page :category :type :alias :version]
		  query-table:: true
	- **Note**
- <p style="font-size: 20px; font-weight: bold; color: #61DBFB">React</p>
	- 📚 [[React 學習筆記]]
	- **Hooks**
	  collapsed:: true
		- {{query (and (property :type "#React") (property :type "#Hooks"))}}
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
	- **Vue2**
	  collapsed:: true
		- {{query (property :type "#Vue2")}}
		  query-table:: true
		  query-properties:: [:page :type :version]
	- **Vue3**
	  collapsed:: true
		- {{query (property :type "#Vue3")}}
		  query-table:: true
		  query-properties:: [:page :category :type :alias :version]
- **HTML**
	- [[HTML - 換行符不生效問題]]
	- [[HTML - Table Scroll With HTML and CSS]]
- <p style="font-size: 20px; font-weight: bold; color: #215732;">Node.js</p>
  collapsed:: true
	- {{query (property :type "#Node.js")}}
	  query-properties:: [:page :category :type :alias]
	  query-table:: true
- <p style="font-size: 20px; font-weight: bold; color: #0db7ed;">Docker</p>
  collapsed:: true
	- [[multi-stage builds (多階段構建)]]
	- [[Docker-desktop 空間不足]]
	- [[Docker 與 Podman 的差異點]]
	- [[Docker container 資料持久化]]
	- [[Pass environment variables from docker to Node.js]]
	- **Docker Compose**
		- [[Compose file - ports]]
- <p style="font-size: 20px; font-weight: bold; color: #43A047;">Nginx</p>
  collapsed:: true
	- [[Nginx config]]
		- [[Nginx config - https]]
		- [[Nginx config - server]]
		- [[Nginx config - upstream]]
		- [[Nginx config - location]]
- <p style="font-size: 20px; font-weight: bold; color: #000;">Pattern 設計模式</p>
  collapsed:: true
	- [[狀態模式 State]]
	- [[策略模式 Strategy]]
	- [[觀察者模式 Observer]]