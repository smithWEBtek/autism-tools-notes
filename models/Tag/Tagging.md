<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

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
t.integer :board_id
t.integer :resource_id
t.integer :diet_id
t.integer :meal_id
t.integer :recipe_id
t.integer :document_id
t.integer :medication_id
t.integer :playlist_id
t.integer :schedule_id
t.integer :treatment_id
t.integer :user_id
```

### migration

```
$ rails g resource Tagging tag_id:integer board_id:integer resource_id:integer diet_id:integer meal_id:integer recipe_id:integer document_id:integer medication_id:integer playlist_id:integer schedule_id:integer treatment_id:integer user_id:integer
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
belongs_to :user, optional: true
```

### serializer

```ruby
class TaggingSerializer < ActiveModel::Serializer
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
  belongs_to :user, optional: true
end
```
