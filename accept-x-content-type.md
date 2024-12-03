# Accept X Content-Type

- Accept
  o que vou receber

- Content Type
  o que vou enviar

Content-Type: application/vnd.api+json

```ruby
  def ensure_json_request
    unless request.headers['Accept'] =~ /vnd\.api\+json/
      render nothing: true, status: 406
    else
      unless request.get?
        return if request.headers['Content-Type'] =~ /vnd\.api\+json/
        render nothing: true, status: 415
      end
    end
  end
```

## JSON API Specification

http://jsonapi.org/format/#content-negotiation
