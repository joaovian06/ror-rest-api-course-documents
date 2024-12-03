# Hostname and Subdomain

sudo vim /etc/hosts

```shell
127.0.0.1 meusite.local
127.0.0.1 localhost
127.0.0.1 v1.localhost
127.0.1.1 joaovian06-lenovo
```

```ruby
# config/routes
constraints subdomain: 'v1' do
  scope module: 'v1' do
    resources :contacts do
      ...
    end
  end
end
```

```ruby
  # config/environments/development.rb
  config.action_dispathc.tld_length = 0
```
