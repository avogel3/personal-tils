# Inline Gemfile with Bundler

### 07/27/2020

Instead of generating a Gemfile for a ruby script you can define one inline like so:

```ruby
# script.rb
require 'bundler/inline'

gemfile do 
  gem 'harvesting'
end

client = Harvesting::Client.new
# ...

```

Everytime you run `ruby script.rb`, bundler will ensure the dependencies are installed and then run your script. 

H/T to [Nithin Bekal's Article on Bundler](https://nithinbekal.com/posts/bundler-inline-gemfile/)

Tags: Ruby, Bundler
