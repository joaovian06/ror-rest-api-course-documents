# sign up

```http
POST http://localhost:3000/auth
{
    "email": "<email>",
    "password": "<pass>",
    "password_confirmation": "<pass>"
}
```

# sign in

```http
POST http://localhost:3000/auth/sign_in
{
    "email": "<email>",
    "password": "<pass>"
}
```

# token header format

- `access-token`:

  ***

  funciona como a senha do usuario para cada request, uma versao e armazada em Hash no banco de dados para comparacao futura, o valor muda a cada request.

- `token-type`:

  ***

  informa sobre o tipo de token utilizado para autenticacao

- `client`:
  ***
  permite o uso de multipla sessoes simultaneas em diferentes clients, por exemplo o usuario quer estar autenticado no celular e no computador ao mesmo tempo
- `expiry`:
  ***
  a data em que a sessao atual ira expirar, pode ser usado para expirar tokens sem a necessidade de uma API request
- `uid`:
  ***
  valor unico utilizado para identificar o usuario, e necessario pois procurar por usuarios no banco de dados pelo token de acesso torna a API suscetivel a Timing Attacks

# Acessando um recurso protegido

- Postman

```http
POST http://localhost:3000/kinds
```

- Curl

```shell
curl -X GET http://localhost:3000/kinds -H 'access-token: <token>' -H 'client: <client>' -H 'uid: <uid>' -H 'Content-type: application/json' -H 'Accept: application/vnd.api+json'
```
