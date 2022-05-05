# S3B11 API

Esse é o repositório com a "API" criada com JSON-Server + JSON-Server-Auth e com deploy no Heroku.

## Base URL

https://primeiro-teste-osmar.herokuapp.com/

## API Endpoints

### Cadastro

POST /register <br/>
POST /signup <br/>
POST /users

example:

> https://primeiro-teste-osmar.herokuapp.com/register

```
{
  "email": "kenzinho@mail.com",
  "password": "123456",
  "name": "Kenzinho",
  "age": 38,
}
```

Resposta:

> 201 OK

```
{
  "email": "kenzinho@mail.com",
  "password": "123456",
  "name": "Kenzinho",
  "password": $2a$10$YQiiz0ANVwIgpOjYXPxc0O9H2XeX3m8OoY1xk7OGgxTnOJnsZU7FO",
  "age": 38,
}
```

---

### Login

POST /login <br/>
POST /signin

```
{
  "email": "kenzinho@mail.com",
  "password": "123456",
}
```

Resposta:
> 200 OK

```
{
  "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJlbWFpbCI6ImtlbnppbmhvQG1haWwuY29tIiwiaWF0IjoxNjUxNzg1ODEzLCJleHAiOjE2NTE3ODk0MTMsInN1YiI6IjEifQ.-0tPRjeuvGAVClysTpJFFkZ1zPc27lceK-tWVeqEGUo",
  "user": {
	  "email": "kenzinho@mail.com",
	  "name": "Kenzinho",
	  "age": 38,
	  "id": 1
  }
}
```

---

### Games

GET /games

#### Necessita autenticação, e ownership:

POST /games

Resposta:
> 200 OK

```
{
	"name": "Dota 2",
	"type": "MOBA",
	"userId": 1
}
```

DELETE /games/:id

Resposta:
> 200 OK

PATCH /games/:id

```
{
	"name": "Dota 3"
}
```
**somente enviar o parametro a ser modificado a ser modificado**

---

### Friends

#### Necessita de autenticação:

GET /friends

#### Necessita de autenticação e ownership:

POST /friends

Resposta:
> 200 OK

```
{
	"name": "Odin",
	"server": "Azralon",
	"userId": 1
}
```

DELETE /friends/:id

Resposta:
> 200 OK