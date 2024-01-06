verbos http
localhost:3000/rails/info/routes

GET
curl http://localhost:3000/contacts

POST
curl http://localhost:3000/contacts -v -i -X POST -H "Content-Type: application/json" -d '{"name": "Joao", "email": "joaovitorvian"}'

GET
curl http://localhost:3000/contacts/101

PUT - todos itens do recurso
PATCH - apenas alguns campos
curl http://localhost:3000/contacts/101 -v -i -X PATCH -H "Content-Type: application/json" -d '{"name": "joao vian"}'

DELETE
curl http://localhost:3000/contacts/101 -i -v -X DELETE
