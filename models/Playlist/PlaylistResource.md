<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [class PlaylistResource](#class-playlistresource)
  - [columns](#columns)
  - [migration](#migration)
  - [ar relationships](#ar-relationships)
  - [serializer](#serializer)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## class PlaylistResource

### columns

```ruby
  t.integer :playlist_id
  t.integer :resource_id
```

### migration

```ruby
$ rails g resource PlaylistResource playlist_id:integer resource_id:integer
```

### ar relationships

```ruby
class PlaylistResource
  belongs_to :playlist
  belongs_to :resource
end
```

### serializer

```ruby
class PlaylistResourceSerializer < ActiveModel::Serializer
  belongs_to :playlist
  belongs_to :resource
end
```
