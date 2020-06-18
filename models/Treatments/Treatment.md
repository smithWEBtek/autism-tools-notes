<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [class Treatment](#class-supplement)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Treatment

### columns

```ruby
t.string :name
t.text :description
t.text :instructions
```

### migration

```
$ rails g resource Treatment name:string description:text instructions:text
```

### ar relationships

```ruby
  has_many :regimens
  has_many :taggings
  has_many :tags, through: :taggings
```

### serializer

```ruby
class TreatmentSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :instructions
  has_many :regimens
  has_many :taggings
  has_many :tags, through: :taggings
end
```
