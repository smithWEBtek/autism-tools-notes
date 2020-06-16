## class Meal

### columns

```ruby
t.string :name
t.integer :diet_id
t.text :description
```

### migration

```ruby
$ rails g resource Meal name:string description:text diet_id:integer
```

### ar relationships

```ruby
class Meal
  belongs_to :diet
end
```

### serializer

```ruby
class MealSerializer < ActiveModel::Serializer
  attributes :id, :name, :description
  belongs_to :diet
end
```
