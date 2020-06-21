<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [class Resource](#class-resource)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Resource

### columns

```ruby
t.string :name
t.text :description
t.string :format
t.string :location
```

### migration

```
$ rails g resource resource name:string description:text
format:string location:string
```

### ar relationships

```ruby
  has_many :board_resources
  has_many :boards, through: :board_resources
  has_many :taggings
  has_many :tags, through: :taggings, source: :resource
```

### serializer

```ruby
class ResourceSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :format, :location
  has_many :board_resources
  has_many :boards, through: :board_resources
  has_many :taggings
  has_many :tags, through: :taggings, source: :resource
end
```
