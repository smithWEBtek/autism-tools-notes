<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [class Recipe](#class-recipe)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

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
  has_many :taggings
  has_many :tags, through: :taggings, source: :recipe
end
```

### serializer

```ruby
class RecipeSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :instructions
  has_many :taggings
  has_many :tags, through: :taggings, source: :recipe
end
```
