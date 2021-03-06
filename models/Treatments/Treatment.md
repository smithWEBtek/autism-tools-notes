<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [class Treatment](#class-treatment)
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
```

### migration

```
$ rails g resource Treatment name:string description:text
```

### ar relationships

```ruby
  has_many :steps
  has_many :medications, through: :steps
  has_many :supplements, through: :steps
  has_many :taggings
  has_many :tags, through: :taggings
```

### serializer

```ruby
class TreatmentSerializer < ActiveModel::Serializer
  attributes :id, :name, :description
  has_many :steps
  has_many :medications, through: :steps
  has_many :supplements, through: :steps
  has_many :taggings
  has_many :tags, through: :taggings
end
```
