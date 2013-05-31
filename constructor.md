# Constructor

```objc
[[Foo alloc] init]

Camembert *camembert = [[Camembert alloc] initWithAge:3 smell:someSmell];
```

Ruby:

```ruby
class Object
  def self.new(*args)
    self.alloc.initialize(*args)
  end

  def initialize
  end
end
```
