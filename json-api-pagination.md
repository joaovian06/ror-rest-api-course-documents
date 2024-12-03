# JSON API Pagination

https://jsonapi.org/format/#fetching-pagination

```ruby
  def index
    # @contacts = Contact.all.page(params[:page][:number]).per(params[:page][:size])
    @contacts = Contact.all.page(params[:page] ? params[:page][:number] : 1).per(params[:page][:size])
    # .try(:[], :number)

    render json: @contacts
  end
```
