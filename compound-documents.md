compound-documents.md

fetching - busca de dados
reduzir numero de requisicoes http
evitar colocar dados, e apenas linkar os relacionamentos

- links devem ser baseados em formatacao rest
  url/resource/:id/resource_relationship

```ruby
# routes.rb
resources :contacts do
    resource :kind, only: [:show]
    resource :kind, only: [:show], path: "relationships/kind"
end

# contact_kind
# GET /contacts/:contact_id/kind(.:format)
# kinds#show
```
