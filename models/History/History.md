<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [class History](#class-history)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class History

### columns

```ruby
t.integer :user_id
t.integer :tag_id, default: nil
t.integer :board_id, default: nil
t.integer :resource_id, default: nil
t.integer :diet_id, default: nil
t.integer :meal_id, default: nil
t.integer :recipe_id, default: nil
t.integer :document_id, default: nil
t.integer :treatment_id, default: nil
t.integer :medication_id, default: nil
t.integer :supplement_id, default: nil
t.integer :playlist_id, default: nil
t.integer :event_id, default: nil
```

### migration

```
$ rails g resource History tag_id:integer board_id:integer resource_id:integer diet_id:integer meal_id:integer recipe_id:integer document_id:integer medication_id:integer playlist_id:integer schedule_id:integer treatment_id:integer
```

### ar relationships

```ruby
belongs_to :board, optional: true
belongs_to :resource, optional: true
belongs_to :diet, optional: true
belongs_to :meal, optional: true
belongs_to :recipe, optional: true
belongs_to :document, optional: true
belongs_to :medication, optional: true
belongs_to :playlist, optional: true
belongs_to :schedule, optional: true
belongs_to :treatment, optional: true
```

### serializer

```ruby
class HistorySerializer < ActiveModel::Serializer
  attributes :id, :name
  belongs_to :board, optional: true
  belongs_to :resource, optional: true
  belongs_to :diet, optional: true
  belongs_to :meal, optional: true
  belongs_to :recipe, optional: true
  belongs_to :document, optional: true
  belongs_to :medication, optional: true
  belongs_to :playlist, optional: true
  belongs_to :schedule, optional: true
  belongs_to :treatment, optional: true
end
```
