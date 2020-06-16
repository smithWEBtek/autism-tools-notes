<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [class Tag](#class-tag)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Tag

### columns

```ruby
t.string :name
```

### migration

```
$ rails g resource Tag name:string
```

### ar relationships

```ruby
has_many :taggings
```

### serializer

```ruby
class TagSerializer < ActiveModel::Serializer
  attributes :id, :name
  has_many :boards
  has_many :resources
  has_many :diets
  has_many :meals
  has_many :recipes
  has_many :documents
  has_many :medications
  has_many :playlists
  has_many :schedules
  has_many :treatments
  has_many :users
end
```
