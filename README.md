# content-library-app-sample
Live [content-library-app-sample](https://rickyharor.github.io/content-library-app-sample/)

## HTML Content Topic page

 **index.html** represents the HTML page that would appear in the content tool of the LMS. The name of this file can be whatever you want, it doesn't have to be called index.html.

Define the sections variable in the `<head>` element with the id values of the content item objects that you would like to have generated on this page.

```html
<script>
  window.sections = [0, 1, 2, 3, 4];
</script>
```

Add a div tag with the `content-library` id and blow it include a call to index.js in the repo.

```html
<div id="content-library">
<script src="https://rickyharor.github.io/content-library-app-sample/index.js"></script>
```

Complete file: [index.html](https://github.com/RickyHaror/content-library-app-sample/blob/master/index.html)

## index.js
This file injects the content-library-app into each HTML content page that references this file.

If there is a change to the code, the structure of the code, the name of the content-library-app .js files, you will only have one file to update.

The GitHub Pages URL to the **databse.json** file is [https://**rickyharor**.github.io/**content-library-app-sample**/database.json](https://rickyharor.github.io/content-library-app-sample/database.json)
Add database variables to index.js.

```javascript
window.databaseHost = 'rickyharor';
window.databaseRepoPath = 'content-library-app-sample';
```

Next, add the `<app-root></app-root>` tag to the `<div> id"content-library"></div>`. This tag is specific to how this application works and that may change in the future and that's why it's added here and not in the index.html page.

```javascript
document.getElementById('content-library').innerHTML = '<app-root></app-root>';
```

Finally, add references to the applications .js files in the order specified.

```javascript
var script1 = document.createElement("script");    
script1.src = 'https://RickyHaror.github.io/content-library-app/runtime.js';    
document.getElementsByTagName("body")[0].appendChild(script1); 
  
var script2 = document.createElement("script");    
script2.src = 'https://RickyHaror.github.io/content-library-app/polyfills.js';    
document.getElementsByTagName("body")[0].appendChild(script2);   
 
var script3 = document.createElement("script");    
script3.src = 'https://RickyHaror.github.io/content-library-app/main.js';    
document.getElementsByTagName("body")[0].appendChild(script3);
```

Complete file: [index.js](https://github.com/RickyHaror/content-library-app-sample/blob/master/index.js)
