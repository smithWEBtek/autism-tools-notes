<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

**Table of Contents** _generated with [DocToc](https://github.com/thlorenz/doctoc)_

- [class Meal](#class-meal)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Meal

### columns

```ruby
t.string :name
t.integer :diet_id
t.text :description
```

### migration

```ruby
$ rails g resource Meal name:string description:text
```

### ar relationships

```ruby
class Meal
  has_many :diet_meals
  has_many :diets, through: :diet_meals
  has_many :taggings
  has_many :tags, through: :taggings, source: :meal
end
```

### serializer

```ruby
class MealSerializer < ActiveModel::Serializer
  has_many :diet_meals
  has_many :diets, through: :diet_meals
  has_many :taggings
  has_many :tags, through: :taggings, source: :meal
end
```
