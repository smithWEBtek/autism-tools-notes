<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [class Step](#class-step)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class Step

### columns

```ruby
t.integer :treatment_id
t.integer :step_number
t.string :name
t.text :description
t.text :instructions
t.integer :medication_id, default: nil
t.integer :supplement_id, default: nil
t.integer :dose_qty, default: nil
t.string :dose_unit, default: nil
t.string :dose_description, default: nil
t.datetime :dose_start, default: nil
t.datetime :dose_end, default: nil
```

### migration

```
$ rails g resource Step treatment_id:integer step_number:integer name:string description:text instructions:text medication_id:integer supplement_id:integer dose_qty:integer dose_unit:string dose_description:text dose_start:datetime dose_end:datetime
```

### ar relationships

```ruby
  belongs_to :treatment
  belongs_to :medication, optional: true
  belongs_to :supplement, optional: true
  has_many :taggings
  has_many :tags, through: :taggings
```

### serializer

```ruby
class StepSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :instructions, :regimen_step_number, :medication_id, :supplement_id, :dose_qty, :dose_description, :dose_start, :dose_end

  attributes :id, :treatment_id, :step_number, :name, :description, :instructions, :medication_id, :supplement_id, :dose_qty, :dose_unit, :dose_description, :dose_start, :dose_end
  belongs_to :medication, optional: true
  belongs_to :supplement, optional: true
  has_many :taggings
  has_many :tags, through: :taggings
end
```
