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
t.string :name
t.text :description
t.integer :step_number
t.integer :drug_id, default: nil
t.integer :supplement_id, default: nil
t.integer :dosage_qty
t.string :dosage_description
t.datetime :dosage_start
t.datetime :dosage_end
```

### migration

```
$ rails g resource Step name:string description:text regimen_step_number:integer drug_id:integer supplement_id:integer dosage_qty:integer dosage_description:text dosage_start:datetime dosage_end:datetime
```

### ar relationships

```ruby
  has_many :regimen_steps
  has_many :regimens, through: :regimen_steps
  belongs_to :drug, optional: true
  belongs_to :supplement, optional: true
  has_many :taggings
  has_many :tags, through: :taggings
```

### serializer

```ruby
class DrugSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :regimen_step_number, :drug_id, :supplement_id, :dosage_qty, :dosage_description, :dosage_start, :dosage_end
  has_many :regimen_steps
  has_many :regimens, through: :regimen_steps
  belongs_to :drug, optional: true
  belongs_to :supplement, optional: true
  has_many :taggings
  has_many :tags, through: :taggings
end
```
