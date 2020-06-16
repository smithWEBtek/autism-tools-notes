## class Tagging

### columns

```ruby
t.string :name
t.integer :board_id
t.integer :diet_id
t.integer :document_id
t.integer :medication_id
t.integer :playlist_id
t.integer :resource_id
t.integer :schedule_id
t.integer :treatment_id
t.integer :user_id
```

### migration

```
$ rails g resource resource name:string description:text
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
  attributes :id, :name, :description
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
