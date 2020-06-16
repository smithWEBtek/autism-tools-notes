<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [FEATURE: Playlist](#feature-playlist)
  - [description and user stories](#description-and-user-stories)
  - [class Playlist](#class-playlist)
    - [columns](#columns)
    - [migration](#migration)
    - [ar relationships](#ar-relationships)
    - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# FEATURE: Playlist

## description and user stories

- A Playlist is a grouping of audio and/or video resources
- Resource model is used for this, same as the Pictureplaylist
- Organize playlists from a library of resources
- Store resources on Cloudinary for fast, secure retrieval

## class Playlist

### columns

```ruby
  t.integer :category_id
  t.text :description
  t.string :name
```

### migration

```ruby
$ rails g resource playlist name:string description:text
```

### ar relationships

```ruby
class Playlist
  has_many :resource_categories
  has_many :categories, through: :resource_categories
  has_many :playlist_resources
  has_many :playlists, through: :playlist_resources
end
```

### serializer

```ruby
class playlistSerializer < ActiveModel::Serializer
  attributes :id, :name, :description
  has_many :resource_categories
  has_many :categories, through: :resource_categories
  has_many :playlist_resources
  has_many :playlists, through: :playlist_resources
end
```
