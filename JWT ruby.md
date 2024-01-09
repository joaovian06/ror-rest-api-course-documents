JWT ruby.md

gem 'jwt'

run bundle install

```ruby
hmac_secret = "my$ecretK3y"

payload = { data: "joao vian"  }

token = JWT.encode payload, hmac_secret, 'HS256'

eyJhbGciOiJIUzI1NiJ9.eyJkYXRhIjoiam9hbyB2aWFuIn0.PqXpSE5DvbarYO1RVUvXIVu1mJHzEevnN2spwoUhJMA

decoded_token = JWT.decode token, hmac_secrect, true, { algorithm: 'HS256' }

[{"data"=>"joao vian"}, {"alg"=>"HS256"}]
```
