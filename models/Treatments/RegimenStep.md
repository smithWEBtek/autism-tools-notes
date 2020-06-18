<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [class RegimenStep](#class-regimenstep)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class RegimenStep

### columns

```ruby
t.integer :regimen_id
t.integer :step_id
```

### migration

```
$ rails g resource RegimenStep regimen_id:integer step_id:integer
```

### ar relationships

```ruby
  belongs_to :regimen
  belongs_to :step
```

### serializer

```ruby
class RegimenStepSerializer < ActiveModel::Serializer
  attributes :id, :regimen, :step
  belongs_to :regimen
  belongs_to :step
end
```
