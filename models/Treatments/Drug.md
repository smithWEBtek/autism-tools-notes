<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [class Drug](#class-drug)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Drug

### columns

```ruby
t.string :name
t.text :description
```

### migration

```
$ rails g resource Drug name:string description:text
```

### ar relationships

```ruby
  has_many :dosages
  has_many :taggings
  has_many :tags, through: :taggings
```

### serializer

```ruby
class DrugSerializer < ActiveModel::Serializer
  attributes :id, :name, :description
  has_many :dosages
  has_many :taggings
  has_many :tags, through: :taggings
end
```
