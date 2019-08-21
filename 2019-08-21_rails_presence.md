# Presence Method (Rails)

### 8/21/2019

Presence is a Rails method that check for the presence of an item, and returns nil if it is not there:

```ruby
user = params[:user] if params[:user].present?

## The above code can be written as

user = params[:user].presence
```
[Ruby on Rails API Doc](https://api.rubyonrails.org/classes/Object.html#method-i-presence)

h/t to [marybethlee](github.com/marybethlee)

