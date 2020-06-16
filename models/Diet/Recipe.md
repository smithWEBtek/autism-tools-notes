## class Recipe

### columns

```ruby
t.string :name
t.text :description
t.text :instructions
```

### migration

```ruby
$ rails g resource Recipe name:string description:text instructions:text
```

### ar relationships

```ruby
class Recipe
end
```

### serializer

```ruby
class RecipeSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :instructions
end
```
