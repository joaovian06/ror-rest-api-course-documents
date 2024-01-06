rest x restful

- rest - respresentational state transfer

  - criado em 2000 por Roy fielding
  - formalizacao de conjunto de melhores praticas denominadas constraints

  - constraints
    - cliente e servidor
      - separar responsabilidades de diferentes partes do sistema
    - stateless
      - cada requisicao nao deve ter ligacao com requisicoes anteriores ou futuras, deve conter todas infos necessarias
    - cache
      - para melhor performance, response deve ser passivel de cache
    - interface uniforme
      - recursos
      - mensagens autodescritivas
      - hypermedia
    - sistema em camadas
      - capacidade de adicionar elementos intermediarios que sejam transparentes para seus clientes. e.g. Load Balancer
      - permite escalar
    - codigo sobre demanda (opcional)
      - aumentar flexibilidade do cliente
        - codigo JS so e baixado quando determinada pagina e carregada
        - pode trazer problemas de seguranca pois o cliente nao sabe o que esta sendo baixado

- se temos uma api que nao segue os principios REST temos apenas uma api http
- se temos uma api que implementa todas essas constraints estamos falando de uma implementacao RESTful
