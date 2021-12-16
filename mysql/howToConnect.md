## How To connect db


// 1. Create the mysql

````javascript
var mysql      = require('mysql');
var dbconnection = mysql.createConnection({
  host     : 'localhost',
  user     : 'root',
  password : 'secret',
  database : 'example' //if you don't input database, when you use query method, it gives error because no database selected.
});

dbconnection.connect((err) => {
  if (err) {
    throw err;
  } else {
    console.log('connected!');
  }
});

connection.query('SELECT 1 + 1 AS solution', function (error, results, fields) {
  if (error) throw error;
  console.log('The solution is: ', results[0].solution);
});

````

// 2. Use schema.sql to create table's descrition at once.
(run with "mysql -u root < database/schema.sql" in the terminal)

In the schema.sql file, you input the below as an example.

/*
CREATE DATABASE
USE DATABASE
CREATE TABLE
INSERT VALUES
*/

// 3. Require the db folder path in the server file.