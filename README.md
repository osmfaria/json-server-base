# S3B11 API

# json-server-base

Esse é o repositório com a "API" criada com JSON-Server + JSON-Server-Auth e com deploy no Heroku.

## Base URL

https://primeiro-teste-osmar.herokuapp.com/

## API Endpoints

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

example:

``{
"email": "kenzinho@mail.com",
"password": "$2a$10$YQiiz0ANVwIgpOjYXPxc0O9H2XeX3m8OoY1xk7OGgxTnOJnsZU7FO",
"name": "Kenzinho",
"age": 38,
}``

### Login

POST /login <br/>
POST /signin
