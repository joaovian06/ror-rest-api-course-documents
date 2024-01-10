# Host versioning

sudo vim /etc/hosts

```shell
127.0.0.1 meusite.local
127.0.0.1 localhost
127.0.1.1 joaovian06-lenovo
```

add host at

```ruby
# config/environment/development.rb
config.hosts << "meusite.local:3000"
```
