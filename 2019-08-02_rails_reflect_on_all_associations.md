# Reflect On All Associations (Rails)

### 8/2/2019

Ever need to find out associations while inside a rails console? Rails has a great method called `reflect_on_all_associatons` that returns an array of associations on your object.


```ruby
User.reflect_on_all_associations
```

Relevent Link: [Rails API Docs](https://api.rubyonrails.org/classes/ActiveRecord/Reflection/ClassMethods.html#method-i-reflect_on_all_associations)

Tags: Rails, Ruby, general
