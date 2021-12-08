---
id: 02a0026c-6fa1-4040-a4b3-95a9d5a3a299
title: Lib-mysql
desc: ''
updated: 1598636170261
created: 1598636170261

---
[[l.node.lib.mysql]]


# Res
- https://github.com/felixge/node-mysql/
- https://github.com/mysqljs/mysql

# Example

var mysql      = require('mysql');
var connection = mysql.createConnection({
  host     : 'example.org',
  user     : 'bob',
  password : 'secret'
});

connection.connect(function(err) {
  if (err) {
    console.error('error connecting: ' + err.stack);
    return;
  }

  console.log('connected as id ' + connection.threadId);
});

### Eg 2

```
connection.connect()

connection.query('SELECT 1 + 1 AS solution', function (err, rows, fields) {
  if (err) throw err

  console.log('The solution is: ', rows[0].solution)
})

connection.end()


```
