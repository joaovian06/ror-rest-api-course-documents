token-auth-rails.md

```ruby
  include ActionController::HttpAuthentication::Token::ControllerMethods

TOKEN = "ojefnasi094845hrwefwiauh229384tn358f7nf5ethf974"

before_action :authenticate

def authenticate
    authenticate_or_request_with_http_token do |token, options|
        ActiveSupport::SecurityUtils.secure_compare(
            ::Digest::SHA256.hexdigest(token)
            ::Digest::SHA256.hexdigest(TOKEN)
        )
    end
end
```

curl request
curl http://localhost:3000/kinds -H "Accept: application/vnd.api+json" -H "Authorization: Token secret123"
