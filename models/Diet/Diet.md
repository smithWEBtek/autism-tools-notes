<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [FEATURE: Diets](#feature-diets)
  - [description and user stories](#description-and-user-stories)
  - [class Diet](#class-diet)
    - [columns](#columns)
    - [migration](#migration)
    - [ar relationships](#ar-relationships)
    - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# FEATURE: Diets

## description and user stories

- a Diet has
- a name, description, instructions and meals
- a display of intended meal
- a meal form to record actual eaten
- shopping list
- do's and don'ts in the instructions

## class Diet

### columns

```ruby
t.string :name
t.text :description
t.text :instructions
```

### migration

```ruby
$ rails g resource Diet name:string description:text instructions:text
```

### ar relationships

```ruby
class Diet
  has_many :meals
end
```

### serializer

```ruby
class DietSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :instructions
  has_many :diet_meals
  has_many :meals, through: :diets
end
```
