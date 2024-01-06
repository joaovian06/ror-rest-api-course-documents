render-JSON-and-Fix-Auto-Reloading.md

- fix auto-reloading
  - `config/enviroment/development.rb`
    ```ruby
        config.file_watcher = ActiveSupport::FileUpdateChecker
    ```
- render JSON

  - transforma objeto em JSON
  - por baixo dos panos chama `.as_json` e `.to_json`no objeto passado
  - Active Support JSON
    - `.decode`
      - decodifica JSON para Hash
    - `.encode`
      - codifica Hash para JSON
      - alternativa seria o .to_json
  - Active Model Serializer
    - `.as_json`
      - transforma objeto em Hash e podemos aplicar o .to_json
    - `.from_json`
  - `render json: @object, root: true`
    - vem com a raiz:
      object: {}
  - `only`

    - filtra campos que serao enviados no json para apenas os campos informados
      `render json: @object, only: [:name, :email]`

  - `except`

    - filtra campos que serao enviados no json exceto os campos informados
      `render json: @object, except: [:name, :email]`

  - map & merge
    - index:
      - `@objects.map {|object| object.attributes.merge({author: "joao"})}`
    - show:
      - `@object.attributes.merge({author: "joao"})`
  - methods
    - no controller action index:
      - `render json: @objects, methods: :author`
    - no model methodo author
      ```ruby
      def author
        "Joao"
      end
      ```
  - `.as_json`
    - para padronizar no model:
      ```ruby
      def as_json(options={})
        super(methods: :author, root: true)
      end
      ```
