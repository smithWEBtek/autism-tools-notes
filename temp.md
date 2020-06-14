<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [FEATURE: Treatment](#feature-treatment)
  - [description and user stories](#description-and-user-stories)
  - [class Treatment](#class-treatment)
    - [columns](#columns)
    - [migration](#migration)
    - [ar relationships](#ar-relationships)
    - [serializer](#serializer)
  - [class Step](#class-step)
    - [descriptions and user stories](#descriptions-and-user-stories)
    - [columns](#columns-1)
    - [migration](#migration-1)
    - [ar relationships](#ar-relationships-1)
    - [serializer](#serializer-1)
  - [class Medicine](#class-medicine)
    - [descriptions and user stories](#descriptions-and-user-stories-1)
    - [columns](#columns-2)
    - [migration](#migration-2)
    - [ar relationships](#ar-relationships-2)
    - [serializer](#serializer-2)
  - [class Therapy](#class-therapy)
    - [descriptions and user stories](#descriptions-and-user-stories-2)
    - [columns](#columns-3)
    - [migration](#migration-3)
    - [ar relationships](#ar-relationships-3)
    - [serializer](#serializer-3)
  - [class Supplement](#class-supplement)
    - [descriptions and user stories](#descriptions-and-user-stories-3)
    - [columns](#columns-4)
    - [migration](#migration-4)
    - [ar relationships](#ar-relationships-4)
    - [serializer](#serializer-4)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# FEATURE: Treatment

## description and user stories

- A Treatment is grouping of one or more drugs, therapies, vitamins, health regimens or strategies.
- it is for a User.user_type = "client"
- it is prescribed by a User.user_type ["doctor", "caregiver"]
- it has a treatement_type
- it can be added to a schedule
- it has at lesat one, or more steps
- it has zero or more medicines
- it has zero or more supplements
- it has zero or more therapies
- it has instructions

## class Treatment

### columns

```ruby
  t.string :name
  t.text :description
  t.text :instructions
  t.integer :client_user_id
  t.integer :caregiver_user_id
```

### migration

```ruby
$ rails g resource treatment name:string description:text client_user_id:integer caregiver_user_id:integer
```

### ar relationships

```ruby
class Treatment
  has_many :steps
  has_many :medicines
  has_many :therapies
  has_many :supplements
end
```

### serializer

```ruby
class TreatmentSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :client_user_id, :caregiver_user_id
  has_many :treatement_steps
  has_many :medicines
  has_many :therapies
  has_many :supplements
end
```

---

## class Step

### descriptions and user stories

- a TreatmentStep is a unit of a Treatment
- it has a treatment_step_number: (1 or more chronological steps in a Treatment)
- it can have at one or more of the following IDs:
  - medicine_id
  - therapy_id
  - supplement_id
- it has a description
- it has instructions
- it has a dosage
- it has a dosage_unit
- it has a duration
- it has a quantity

### columns

```ruby
t.integer :medicine_id
t.integer :dosage_quantity
t.integer :dosage_unit
t.integer :duration
t.text :description
t.text :instructions

end
```

### migration

```ruby
$ rails g resource
```

### ar relationships

### serializer

---

## class Medicine

### descriptions and user stories

### columns

### migration

### ar relationships

### serializer

---

## class Therapy

### descriptions and user stories

### columns

### migration

### ar relationships

### serializer

---

## class Supplement

### descriptions and user stories

### columns

### migration

### ar relationships

### serializer
