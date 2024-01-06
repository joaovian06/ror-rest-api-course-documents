render-json-with-associations.md

- include

  - saida aninhada (nested)
  - include: { :kind }
  - include: { kind: { only: :description } }

- methods:
  - saida como atributo

```ruby
  def kind_description
    self.kind.description
  end
  # as_json override
  methods: [:kind_description]
```
