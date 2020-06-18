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
  has_many :playlist_resources
  has_many :playlists, through: :playlist_resources
  has_many :taggings
  has_many :tags, through: :taggings, source: :playlist
end
```

### serializer

```ruby
class playlistSerializer < ActiveModel::Serializer
  attributes :id, :name, :description
  has_many :playlist_resources
  has_many :playlists, through: :playlist_resources
  has_many :taggings
  has_many :tags, through: :taggings, source: :playlist
end
```
