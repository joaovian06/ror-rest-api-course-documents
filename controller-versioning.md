# controller versioning

```ruby
module V1
    # /controller/v1/contacts_controller.rb
    # /controller/v2/contacts_controller.rb
    class ContactsController < ApplicationController

    end
end
```

Scope e Module

```ruby
    # routes.rb
    scope module: "v1" do
    resources :kinds
    resources :contacts do
      resource :kind, only: [:show]
      resource :kind, only: [:show], path: "relationships/kind"

      resource :phones, only: [:show]
      resource :phones, only: [:show], path: "relationships/phones"

      resource :phone, only: [:update, :create, :destroy]
      resource :phone, only: [:update, :create, :destroy], path: "relationships/phones"

      resource :address, only: [:show, :update, :create, :destroy]
      resource :address, only: [:show, :update, :create, :destroy], path: "relationships/address"
    end
  end
```

constraints

```ruby
    resources :contacts, constraints: lambda { |request| request.params[:version] = "1" } do
```
