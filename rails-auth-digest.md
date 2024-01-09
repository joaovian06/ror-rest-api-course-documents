rails-auth-digest.md

```ruby
include ActionController::HttpAuthentication::Digest::ControllerMethods
USERS = {
    "jack" => Digest::MD5.hexdigest(["jack", "Application", "secret"].join(":"))
}

before_action :authenticate

def authenticate
    authenticate_or_request_with_http_digest("Application") do |username|
        USERS|username|
    end
end
```
