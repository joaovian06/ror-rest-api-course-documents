JWT.md

# JSON Web Tokens

https://jwt.io

- open industry standard RFC 7519

- reinvindacar seguranca entre duas partes

- decode, verify and generate JWT

## o q ele tenta resolver?

- tokens sao stateful
- para fazer uma autenticacao stateless, podemos usar JWT
- guarda no proprio token info que o server tem q identificar
- o server precisa ter apenas o segredo para verificar a autenticidade do token que chegou pela requisicao

https://jwt.io/introduction

## Estrutura

- token hexadecimal construido em 3 partes separadas por ponto(.)
  header.payload.signature
  aaaaaa.bbbbbbb.ccccccccc

  - header:
    - contem info encriptada
      - algorithm and token type
  - payload:
    - tambem contem info encriptada
      - data
  - signature:
    - soma das duas primeiras partes, encriptada com o segredo do servidor

pode ter expirar em determinado periodo de tempo
