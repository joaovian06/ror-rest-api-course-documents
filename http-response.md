http-response
curl https://localhost:3000/contacts -v -i
opcao `-i` -> traz o cabecalho junto na reposta

- response
  - start-line
    - request-line
      - versao http usada
    - status-line
      - status da requisicao. e.g. 200 OK
  - header fields
    - metadados, info sobre transferencia de dados a ser manipulada
    - e.g. content-type: application/json
  - empty line
    - separa headers e body
  - message body
    - contem dados enviados do servidor em resposta a requisicao
