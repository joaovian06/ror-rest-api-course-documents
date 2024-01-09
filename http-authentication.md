http-authentication.md

- tipos
  - basica
  - resumida

como e feita?

- Header
  - Authorization: tipo senha-encriptada
  - basica
    - Authorization: Basic encryptedpasswod(base64)
  - digest
    - Authorization: Digest encryptedpasswod(MD5)

```ruby
# Encode64

require 'base64'

Base64.encode64('user:pass')
Base64.strict_encode64('user:pass')

# MD5
require 'digest/md5'

Digest::MD5.hexdigest('user:pass')
```

utilizando curl
curl -u user:senha http://localhost:3000/kinds
