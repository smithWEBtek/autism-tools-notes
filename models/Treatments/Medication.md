<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [class Medication](#class-medication)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Medication

### columns

```ruby
t.string :name
t.text :description
```

### migration

```
$ rails g resource Medication name:string description:text
```

### ar relationships

```ruby
  has_many :taggings
  has_many :tags, through: :taggings
```

### serializer

```ruby
class MedicationSerializer < ActiveModel::Serializer
  attributes :id, :name, :description
  has_many :taggings
  has_many :tags, through: :taggings
end
```
