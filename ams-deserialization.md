ams-deserialization.md

quando serializamos com o padrao do json-api
e recuperamos o json, nao conseguiriamos criar um novo registro utilizando o mesmo formato que veio na response

para isso utilizamos a deserializacao

```ruby
ActiveModelSerializers::Deserialization.jsonapi_parse(params, only: [: title, :content, :author])

# podemos utilizar a opcao :keys depois dos params para mapear atributos que venham como nomes que nao correspodem ao no schema
# ex: { author: :user, date: :created_at }
```
