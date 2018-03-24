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

10. Working with ejs

```shell
npm install ejs -save
```

Show me the code!
```javascript

var express = require('express');
var app = express();
app.set('view engine', 'ejs');
app.set('views', './app/views');

```

And the views have a extension .ejs (will be your html + code of view)
```html

<!DOCTYPE html>
	<html lang="pt-br">
		<head>
			<meta charset="utf-8"/>
			<title>Notícias</title>
		</head>
	<body>

		<h1>Notícias</h1>
		<table>
			<thead>
				<tr>
				<th>id</th>
				<th>titulo</th>
				<th>corpo</th>
			</tr>
			</thead>
			<tbody>
				<% 
				for(var i=0; i < noticias.length;i++) { %>
					<tr>
							<td><%= noticias[i].id %></td>
							<td><%= noticias[i].titulo %></td>
							<td><%= noticias[i].corpo %></td>
					</tr>
				<% } %>
				
			</tbody>
		</table>
	</body>
</html>

```

11. To work with mysql

In shell
```shell

npm install mysql -save

```

```javascript
var db = require('mysql');

module.exports = function(){
    return db.createConnection({
        host: '127.0.0.1',
        user: 'asd',
        password: 'asd',
        database: 'curso_nodejs'
    });
}

var cn = require('../../config/dbConnection')();

cn.query('select * from tb_noticias', function(ex, result){
	res.render('noticias/noticias', 
	{
		noticias: result
	});
});
```


10. To work with mysql