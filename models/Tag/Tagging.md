<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [class Tagging](#class-tagging)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Tagging

### columns

```ruby
t.integer :tag_id
t.integer :board_id, default: nil
t.integer :resource_id, default: nil
t.integer :diet_id, default: nil
t.integer :meal_id, default: nil
t.integer :recipe_id, default: nil
t.integer :document_id, default: nil
t.integer :treatment_id, default: nil
t.integer :step_id, default: nil
t.integer :medication_id, default: nil
t.integer :supplement_id, default: nil
t.integer :playlist_id, default: nil
t.integer :event_id, default: nil
```

### migration

```
$ rails g resource Tagging
tag_id:integer
board_id:integer
resource_id:integer
diet_id:integer
meal_id:integer
recipe_id:integer
document_id:integer
treatment_id:integer
medication_id:integer
supplement_id:integer
playlist_id:integer
event_id:integer
```

### ar relationships

```ruby
belongs_to :tag
belongs_to :board, optional: true
belongs_to :resource, optional: true
belongs_to :diet, optional: true
belongs_to :meal, optional: true
belongs_to :recipe, optional: true
belongs_to :document, optional: true
belongs_to :treatment, optional: true
belongs_to :step, optional: true
belongs_to :medication, optional: true
belongs_to :supplement, optional: true
belongs_to :playlist, optional: true
belongs_to :event, optional: true
```

### serializer

```ruby
class TaggingSerializer < ActiveModel::Serializer
  attributes :id, :tag
  belongs_to :board, optional: true
  belongs_to :resource, optional: true
  belongs_to :diet, optional: true
  belongs_to :meal, optional: true
  belongs_to :recipe, optional: true
  belongs_to :document, optional: true
  belongs_to :treatment, optional: true
  belongs_to :step, optional: true
  belongs_to :medication, optional: true
  belongs_to :supplement, optional: true
  belongs_to :playlist, optional: true
  belongs_to :event, optional: true
end
```
