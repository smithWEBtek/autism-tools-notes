<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->


- [FEATURE: Boards](#feature-boards)
  - [description and user stories](#description-and-user-stories)
  - [class Board](#class-board)
    - [columns](#columns)
    - [migration](#migration)
    - [ar relationships](#ar-relationships)
    - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# FEATURE: Boards

## description and user stories

- Boards have resources (images, giphys, butons) for choices
- Print boards for lamination into a portable booklet
- Organize boards from a library of resources
- Store resources on Cloudinary for fast, secure retrieval

## class Board

### columns

```ruby
  t.integer :category_id
  t.text :description
  t.string :name
```

### migration

```ruby
$ rails g resource Board name:string description:text
```

### ar relationships

```ruby
class Board
  has_many :rcategories
  has_many :board_resources
  has_many :boards, through: :board_resources
end
```

### serializer

```ruby
class BoardSerializer < ActiveModel::Serializer
  attributes :id, :name, :description
  has_many :categories
  has_many :board_resources
  has_many :resources, through: :board_resources
end
```
