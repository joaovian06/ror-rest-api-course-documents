# http header versioning

Accept: application/vnd.api+json; version=1
X-Version: 1.0

```ruby
    # config/routes.rb
    api_version(module: "V1", header: { name: "Accept", value: "application/vnd.api+json; version=1" }) do
    # api_version(module: "V2", header: { name: "X-Version", value: "2.0" }) do
        # resources
    end
```
