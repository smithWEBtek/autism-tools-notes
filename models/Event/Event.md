<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [FEATURE: Event](#feature-event)
  - [description and user stories](#description-and-user-stories)
    - [columns](#columns)
    - [migration](#migration)
    - [ar relationships](#ar-relationships)
    - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# FEATURE: Event

## description and user stories

- Event model captures all activities of a client user.

- Users can
  - schedule events (any duration)
  - schedule recurring events (any duration)
  - enter a name for an Event
  - enter description of an Event
  - select existing Users to add to an Event
  - enter external email address and add it to an Event

### columns

t.string :name
t.text :description
t.datetime :start_time
t.datetime :end_time
t.integer :duration

### migration

\$ rails g resource Event name:string description:text start_time:datetime end_time:datetime duration:integer

### ar relationships

```ruby
has_many :users
```

### serializer

```ruby
attributes :id, :name, :description, :start_time, :end_time, :duration
has_many :users
```
