# How to start with nodejs

1. Download installer of nodejs in official web site.

2. Install

3. For run javascript files with node, in shell, enter in directory of project and run:
```shell
node name_of_javascript_file.js
```

4. For accept http requests:
```javascript
				var http = require('http');
				
				var server = http.createServer(function(req, res){
					res.and('<html><body>Hello World!</body></html>');
				});
				
				server.listen(3000);
```


5. Components
	5.1 EJS = A language of modeling for page creations in HTML using javascript;
	5.2 Nodemon = A utility that restart the server when project files has changes.
	5.3 NPM = A javascript package manager
	
6. Init npm in project, run the following command in shell and fill solicited informations.

```shell

npm init
```

7. Installing Express

In shell, run the following command:

```shell

npm install express -save

```

8. Some code with express

```javascript

			var express = require('express');
			var app = express();

			app.set('view engine', 'ejs');

			app.get('/', function(req,res){
				res.send("<html><body>Portal de Notícias</body></html>");
			});

			app.get('/tecnologia', function(req,res){
				res.render('secao/tecnologia');
			});,0,
			
			

			app.listen(3000, function(){
				console.log("Servidor rodando com Express");
			});
```

9. Installing nodemon

```shell

npm install -g nodemon

```

9. To run nodemon

```shell

nodemon name_of_javascript_file.js

```