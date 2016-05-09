# HTML And CSS Guide

1. General style rules
	- Omit the protocol portion (`http || https`) from URLs point to images and media files
	
	`<script src="///www.google.com/js/jquery.js"></script>`
	``` css
	.example {
		background: url(//www.google.com/imgs/exapmle/jpg);
	}
	```

2. General formatting rules
	- Indet with 2 spances,don't use `tab`
	- Use only lowercase
	``` css
	color: #e5e5e5;
	```
	- Remove trailing white spaces

3. General `meta` rules
	- Use `utf-8` 
	```
	<meta charset="utf-8">
	```
	- Use comments to explain code

4. HTML style rules
	- `<!DOCTYPE html>`
	- Use valid HTML where possiable
	- Don't close void element `<br>`not`<br />`
	- Use HTML according ti its purpoes(标签语义化)
	- Provide alternative contents for multimedia, add `alt` for `img`
	``` html
	<img src="//www.google.com/imgs/example.jpg" alt="example">
	```
	- Keep structure, presentation, behavior apart(结构、表现、行为分离)
	- Omit `type` attributes of `css` and `javascript`

5. HTML formatting rules
	- Use a new line for every block, list, or table element
	``` html
	<blockquote>
		<p>This this a p element</p>
	</blockquote>
		
	<ul>
		<li>HTML</li>
		<li>CSS</li>
		<li>Javascript</li>
	</ul>
		
	<table>
		<!-- content -->
	</table>
	```
	- When quote attribute values, use double quotation marks
	``` html
	<div class="container"></div>
	```
6. CSS style rules
	- Use valid CSS where possiable
	- Use meaningful or genertic ID and class names
	- ID and class name should as short as possiable but as long as necessnary
	- Use shorter properties
	``` css
	.example {
		padding: 0 1em 2em;
		margin: 5px 10px 5px 20px;
		font: 100%/1.6 serif, georia;
	}
	```
	- Omit unit specification after '0' values
	``` css
	margin: 0;
	padding: 0;
	```
	- Omit leading '0' in values
	``` css
	font: .8em;
	opacity: .7;
	```
	- Use 3 character Hex(color) `#fff`
	- Using namespaces helps preventing naming conflicts(**prefixes**)
	
7. CSS formatting rules
	- Alphabetize declaration
	``` css
	background: white;
	border: 1px solid #000;
	border-radius: 50%;
	color: #ddd;
	font-size: 1em;
	text-align: center;
	vertical-align: middel;
	```	
	- Indent all block content
	``` css
	@media screen, projection {
		html {
			background: #ddd;
			color: #333;
		}
	}
	```
	- Use a semicolon after every declaration
	``` css
	.test {
		background-color: #eee;
		color: #333;
	}
	```
	- Use a space after a property name's colon
	```css
	.test {
		background-color:#eee; // missing
		color: #333;
	}	
	```
	- Use a space between the last selector and the declaration block
	``` css
	/* not recommended: missing spaces */ 
	.test{
		/* declaration */
	}
	
	/* not recommended: unnecessary line break */
	.test
	{
		/* declaration */
	}
	
	/* recommended */
	.test {
		/* declaration */
	}
	```
	- Always start a new line for each selector and declaration
	``` css
	h1,
	h2,
	h3 {
		font-weight: normal;
		line-height: 1.2;
	}
	```
	- Separate rules by new lines
	``` css
	html {
		background: #fff;
	}
	
	body {
		margin: 0;
		width: 50%;
	}
	```
