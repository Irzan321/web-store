# User API Spec

## Register User API

Endpoint : POST/api/users

Request Body :

```json
{
  "username": "irzan",
  "password": "12345",
  "name": " M irzan"
}
```

Response Body Succes :

```json
{
  "data": {
    "username": "irzan",
    "name": "M irzan"
  }
}
```

Response Body Failed :

```json
{
  "error": "Username already registered"
}
```

## Loggin User API

Endpoint : POST /api/users/login

Request Body :

```json
{
  "username": "irzan",
  "password": "12345"
}
```

Response Body Succes :

```json
{
  "data": {
    "token": "unique-token"
  }
}
```

Response Body Failed :

```json
{
  "error": " Username or Password wrong"
}
```

## Update User API

Endpoint : PATCH/api/users/current

Headers :

- Authorization : token

Request Body :

```json
{
  "name": "Moh irzan", //optional
  "password": "new password" //optional
}
```

Response Body Succes :

```json
{
  "data": {
    "username": "irzan",
    "name": "M irzan"
  }
}
```

Response Body Failed :

```json
{
  "error": "This name over length"
}
```

## Get User API

Endpoint : GET/api/current

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": {
    "username": "irzan",
    "name": "M irzan"
  }
}
```

Response Body Failed :

```json
{
  "error": " Unauthorized"
}
```

## Logout User API

Endpoint : DELETE/api/users/logout

Headers :

- Authorization : token

Response Body Success :

```json
{
  "data": "DONE"
}
```

Response Body Failed :

```json
{
  "error": "Unauthorized"
}
```
