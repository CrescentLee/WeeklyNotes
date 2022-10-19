## Basic Node and Express

###### Oct-2022

1. Express app requires two line in myApp.js
```javascript
    let express = require('express');
    let app = express();
```
2. General Express App functions
```javascript
    //HTTP method get post
    app.get("/", function(req, res){
        //execute
    })
    app.post("/", function(req, res){
        //execute
    })
    //middleware use, each app.use(middleware) is called every time a request is sent ot the server.
    app.use("/", function(req, res, next){
        //execute
        next();
    })
    //or remove path for overall route
    app.use(function(req, res, next){
        //execute
        next();
    })
    //chain middle ware in request
    app.get("/", function(req, res, next){
        //execute middleware
        next(); //must have
    }, function(req, res){
        //execute
    })
    //some function
    app.get("/", function(req, res){
        //send file
        res.sendFile("xxx.html");
        //send json response
        res.json({....});
    })
    //to use parameter in .env file
    var str = process.env.variable_name;
    //query string
    var str = req.query.variable_name
    //to decode post content
    let bodyParser = require('body-parser');
    app.use(bodyParser.urlencoded({extended:false}));
    app.post('/', function(){
        var str = req.body.variable_name;
    })
```