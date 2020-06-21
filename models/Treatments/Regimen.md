<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [class Regimen](#class-regimen)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Regimen

### columns

```ruby
t.string :name
t.text :description
t.text :instructions
```

### migration

```
$ rails g resource Step name:string description:text instructions:text
```

### ar relationships

```ruby
  has_many :regimen_steps
  has_many :steps, through: :regimen_steps
  has_many :taggings
  has_many :tags, through: :taggings
```

### serializer

```ruby
class RegimenSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :instructions
  has_many :regimen_steps
  has_many :regimens, through: :regimen_steps
  has_many :taggings
  has_many :tags, through: :taggings
end
```
