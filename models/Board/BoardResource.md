<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [class Resource](#class-resource)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Resource

### columns

```ruby
t.integer :board_id
t.integer :resource_id
```

### migration

```
$ rails g resource BoardResource board_id:integer resource_id:integer
```

### ar relationships

```ruby
belongs_to :board
belongs_to :resource
```

### serializer

```ruby
class ResourceSerializer < ActiveModel::Serializer
  attributes :id, :board_id, :resource_id
  belongs_to :board
  belongs_to :resource
end
```
