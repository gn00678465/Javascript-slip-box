## Basic
	- {{query (and (property :type "#Typescript") (not (property :type "#Utility")) (not (property :type "#React")) (not (property :type "#Vue3")) (not (property :category Note)) )}}
	  query-table:: true
	  query-properties:: [:page :category :type :alias :version]
- ## Utility
  query-table:: true
  query-properties:: [:page :category :type :alias]
	- {{query (and (property :type "#Typescript") (property :type "#Utility"))}}
	  query-properties:: [:page :category :type :alias :version]
	  query-table:: true
- ## 📓 Note
	- [[TS - string & {}]]
	- [[Note/TS/Discriminated Unions 範例]]