﻿# contactAPI - An example of REST API in Node.js
<b> Requirements:</b><br>
npm install express; <br>
npm install body-parser;<br>
npm install mysql;<br>
Extract the files from node_modules.zip in the root folder level (../contactAPI/node_modules);<br>

ln - line;

#1 - server.js (../contactAPI/)
1.1 (#ln 2 and 54)- Listen requests on the port setting object or a port defined by the developer <br>
1.2 (#ln 14) - This app got a referenct to the express framework, it expectes a path like this [your domain]/api/contact/:id?<br>
1.3 (#ln 18) - App gets the http Method provided by the request variable and redirects this request to a method from the  "contactController.js" controller <br>

#2 - contactController.js (../contactAPI/controllers/)
2.1 - There are 4 main methods:<br>
	2.1.1 - getContact - handle request with method GET <br>
	2.1.2 - updateContact - handle request with method PUT, a query string and data from a html form are required.<br>
	2.1.3 - insertContact - handle request with method POST, data from a html form is required.<br>
	2.1.4 - deleteContact - handle request with method DELETE<br>
2.2 - contactController creates a instance of dbContact (responsable for create an instance of contactEntity class and other classes related with tables from Database)<br>

#3 - dbContact.js (../contactAPI/models/)
3.1 creates an instance of contactEntity class <br>
	
#4 - contactEntity.js (../contactAPI/models/)
4.1 - handle CRUD operations (INSERT, SELECT, UPDATE and DELETE) in tbContact Table<br>
4.2 - It delegates to the dbDataAccess class these CRUD operations in MySql Database<br>

#5 dbDataAccess.js (../contactAPI/models/)
5.1 - Build the SQL Query according  with the parameters recivided by the contactEntity or other classes classes related with tables from Database.<br>
5.2 - In SELECT command it returns a json object with the data.<br>
5.3 - In modification commands (UPDATE,INSERT and DELETE) it returns a json object with the number of rows affected in table.<br>
