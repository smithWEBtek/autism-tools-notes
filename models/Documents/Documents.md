<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->

- [FEATURE: Docs](#feature-docs)
  - [description and user stories](#description-and-user-stories)
    - [columns](#columns)
    - [migration](#migration)
    - [ar relationships](#ar-relationships)
    - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# FEATURE: Docs

## description and user stories

- Document manager for the Client
- categories of docs
- scans, pdfs, Word docs, notes
- tracking docs
- legal
- procedural
- EIP, therapeutic program
- contractors
- purchasing
- Legal
- Education
- Program
- Medical
- Insurance

### columns

```ruby
t.string :name
t.text :description
t.text :instructions
t.string :format
t.string :location
t.integer :user_id
```

### migration

```ruby
rails g resource Document name:string description:text instructions:text format:text location:text user_id:integer
```

### ar relationships

```ruby
  belongs_to :user
  has_many :taggings
  has_many :tags, through: :taggings, source: :document
```

### serializer

```ruby
class DocumentSerializer < ActiveModel::Serializer
  attributes :id, :name, :description, :instructions, :format, :location, :user
  belongs_to :user
  has_many :taggings
  has_many :tags, through: :taggings, source: :document
end
```
