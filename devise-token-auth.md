Devise
biblioteca modular de autenticacao do Ruby on rails

repo:
https://github.com/platformatec/devise

nao trabalha com token
porem indica o uso da biblioteca devise_token_auth

Devise Token Auth

repo:
https://github.com/lynndylanhurley/devise_token_auth

durante cada request uma novo token e gerado
header `access-token`

config:
no Gemfile:

```ruby
gem "devise"
gem "devise_token_auth"
gem "devise-i18n"
```

no terminal:

```shell
bundle install
rails d devise:install
rails g devise_token_auth:intall User auth
rails db:migrate
```

```ruby
# config/application.rb
# resolve problema para fazer o login e em seguida fazer uma requisicao autenticada para Rails v7
config.session_store :cookie_store, key: '_interslice_session'
config.middleware.use ActionDispatch::Cookies
config.middleware.use config.session_store, config.session_options
```

User é a classe que sera usada para autenticacao
auth é a o caminho utilizado para montar as rotas de autenticacao
