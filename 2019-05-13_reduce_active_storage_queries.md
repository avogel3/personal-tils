# Reduce Active Storage Queries (N+1)

### 05/13/2019

Consider we are using ActiveStorage in a Rails project and we have a model like so:

```ruby
class Document < ApplicationRecord
  has_one_attached :file
end
```

If our controller query for Document(s) does not preload the file, we will have an N+ 1 query on our hands.

Luckily, ActiveStorage includes a method to reduce N+1's. We can use it like so: 

```ruby
Document.with_attached_file
```

Tags: Rails, ActiveStorage, Ruby

