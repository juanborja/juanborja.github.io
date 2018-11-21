---
layout: post
title:  "Node + express"
date:   2018-10-29 20:44:53 -0300
categories: php
---
# Iniciar projecto con express y node

1. Crear una carpeta para el proyecto
2. Dentro d ela carpeta ejecutar npm init
3. Instalo express: npm install express --save
4. Creo archivo app.js en la raiz, con el siguiente codigo

~~~js
var express = require('express');
var app = express();

app.get('/', function (req, res) {
  res.send('Hello World!');
});

app.listen(3000, function () {
  console.log('Example app listening on port 3000!');
});
~~~
5. node app.js
6. npm install mysql
7. Creo la carpeta db con el archivo conexion.js donde voy a guardar los datos de conexion a la bd.
8. En el archivo conexion.js pongo el sigiente codigo

~~~js
module.exports = {query:query} //Exponemos el metodo query

const mysql = require('mysql');
let conexion = null;

function init(){
    conexion = mysql.createConnection({
        host:'127.0.0.1',
        user: 'myuser',
        password: 'mypassword',
        datbase: 'mydb'
    })
}

function query(queryString, callback){
    init();
    conexion.connect();
    conexion.query(queryString, function(error, results, fields){
        console.log ('Error: ', error, 'Result: ', results);
        conexion.end();
        callback(responseObject(error, results));
    }) 

}

function responseObject(error, results){
     return{
         error: error,
         results: results === undefined ? null : results === null ? null : results
     }
}

~~~
9. Instalo body-parser. npm install body-parser


http://expressjs.com/es/starter/installing.html