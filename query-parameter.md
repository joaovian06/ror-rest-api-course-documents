http://localhost:3000/contacts/100?version=1

```ruby
if params[:version] == "1"
    XXXXX
else params[:version] == "2"
    YYYYY
end
```

nada usual pois nao tem como manter esse padrao de repetindo para cada action de cada api controller
fere o principio DRY dont repeat yourself
