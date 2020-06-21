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

- EventUser model joins a user with an event.
- User can have many Events
- Event has_many users

### columns

t.integer :event_id
t.integer :user_id

### migration

\$ rails g resource EventUser event_id:integer user_id:integer

### ar relationships

```ruby
belongs_to :event
belongs_to :user
```

### serializer

```ruby
attributes :id, :event_id, :user_id
belongs_to :event
belongs_to :user
```
