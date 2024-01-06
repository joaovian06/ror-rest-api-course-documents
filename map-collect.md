map-collect.md

```ruby
x = [1,2,3,4]
y = x.map { |i| i*3 } => y = [3,6,9,12]

x.collect! { |i| i*3 } => x = [3,6,9,12]
```
