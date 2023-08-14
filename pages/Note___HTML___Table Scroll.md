category:: Note
type:: #HTML
alias:: Table Scroll With HTML and CSS

- ## Table Scroll With HTML and CSS
	- **結構**
		- ```html
		  <table cellspacing="1" cellpadding="0" border="0">
		    <tr>
		      <td>
		        <table>
		          <tr>
		            <th>Head 1</th>
		            <th>Head 2</th>
		          </tr>
		        </table>
		      </td>
		    </tr>
		    <tr>
		      <td>
		        <div class="table-data">
		          <table>
		            <tr>
		            	<td>Row 1 - Body 1</td>
		              <td>Row 1 - Body 2</td>
		            </tr>
		            <tr>
		            	<td>Row 2 - Body 1</td>
		              <td>Row 2 - Body 2</td>
		            </tr>
		          </table>
		        </div>
		      </td>
		    </tr>
		  </table>
		  ```
	- **CSS**
		- ```css
		  .table-data {
		    width: 150px;
		    height: 150px;
		    overflow-x: auto;
		    overflow-y: auto;
		  }
		  ```
- ## Reference
	- [Table Scroll With HTML and CSS](https://linuxhint.com/table-scroll-with-html-and-css/)