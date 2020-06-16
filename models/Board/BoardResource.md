## class Resource

### columns

```ruby
t.integer :board_id
t.integer :resource_id
```

### migration

```
$ rails g resource BoardResource board_id:integer resource_id:integer
```

### ar relationships

```ruby
belongs_to :board
belongs_to :resource
```

### serializer

```ruby
class ResourceSerializer < ActiveModel::Serializer
  attributes :id, :board_id, :resource_id
  belongs_to :board
  belongs_to :resource
end
```
