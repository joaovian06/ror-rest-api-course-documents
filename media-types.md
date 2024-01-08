media-types.md

media type e uma string que define qual o formato do dado e como ele deve ser lido pela maquina
permite um computador diferenciar um json e xml por exemplo

- exemplos:

  - application/json
  - application/xml
  - multipart/form-data
  - text/html

  - utilizar um header field Accept no momento da resquest

curl http://localhost:3000/contacts/4 -H "
Accept: application/json"

MIME type equivalente a media type e pode ser tambem encontrado como content type

---

```ruby
# application_controller.rb
before_filter :ensure_json_request

def ensure_json_request
    return if request.headers["Accept"] =~ /vnd\.api\+json/
    render nothing: true, status: :not_acceptable
end

# config/initializers/mime_types.rb
Mime::Type.register "application/vnd.api+json", :json
```
