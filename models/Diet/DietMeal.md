<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [DietMeal](#dietmeal)
  - [description and user stories](#description-and-user-stories)
  - [class DietMeal](#class-dietmeal)
    - [columns](#columns)
    - [migration](#migration)
    - [ar relationships](#ar-relationships)
    - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# DietMeal

## description and user stories

- a DietMeal is a single row in the db with a diet_it and a meal_id
- so a meal could belong to many diets via this join table

## class DietMeal

### columns

```ruby
t.integer :diet_id
t.integer :meal_id
```

### migration

```ruby
$ rails g resource DietMeal diet_id:integer meal_id:integer
```

### ar relationships

```ruby
class DietMeal
  belongs_to :diet
  belongs_to :meal
end
```

### serializer

```ruby
class DietSerializer < ActiveModel::Serializer
  attributes :id, :diet, :meal
  belongs_to :diet
  belongs_to :meal
end
```
