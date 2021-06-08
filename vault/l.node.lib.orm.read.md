---
id: 473095ef-cb29-40ce-a318-615f522923a6
title: Read
desc: ''
updated: 1598636170943
created: 1
stub: false
tags: []
url: 'https://www.npmjs.com/package/orm'
---

## --- Quickstart

- normal
```
orm.connect("mysql://username:password@host/database", function (err, db) {
  if (err) throw err;

  var Person = db.define("person", {
    name      : String,
    surname   : String,
    age       : Number, // FLOAT
    male      : Boolean,
    continent : [ "Europe", "America", "Asia", "Africa", "Australia", "Antarctica" ], // ENUM type
    photo     : Buffer, // BLOB/BINARY
    data      : Object // JSON encoded
  }, {
    methods: {
      fullName: function () {
        return this.name + ' ' + this.surname;
      }
    },
    validations: {
      age: orm.enforce.ranges.number(18, undefined, "under-age")
    }
  });

  // add the table to the database
  db.sync(function(err) {
    if (err) throw err;

    // add a row to the person table
    Person.create({ id: 1, name: "John", surname: "Doe", age: 27 }, function(err) {
      if (err) throw err;

      // query the person table by surname
      Person.find({ surname: "Doe" }, function (err, people) {
        // SQL: "SELECT * FROM person WHERE surname = 'Doe'"
        if (err) throw err;

        console.log("People found: %d", people.length);
        console.log("First person: %s, age %d", people[0].fullName(), people[0].age);

        people[0].age = 16;
        people[0].save(function (err) {
          // err.msg == "under-age";
        });
      });
    });
  });
});

```

- express
```
var express = require('express');
var orm = require('orm');
var app = express();

app.use(orm.express("mysql://username:password@host/database", {
    define: function (db, models, next) {
        models.person = db.define("person", { ... });
        next();
    }
}));
app.listen(80);

app.get("/", function (req, res) {
    // req.models is a reference to models used above in define()
    req.models.person.find(...);
});
```
