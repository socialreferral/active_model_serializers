# How to add root key

Add the root key to your API is quite simple with AMS. The **Adapter** is what determines the format of your JSON response. The default adapter is the ```FlattenJSON``` which doesn't have the root key, so your response is something similar to:

```json
{
  "id": 1,
  "title": "Awesome Post Tile",
  "content": "Post content"
}
```

In order to add the root key you need to use the ```JSON``` Adapter, you can change this in an initializer:

```ruby
ActiveModel::Serializer.config.adapter = :json
```

You can also specify a class as adapter, as long as it complies with the AMS adapters interface.
It will add the root key to all your serialized endpoints.

ex:

```json
{
  "post": {
    "id": 1,
    "title": "Awesome Post Tile",
    "content": "Post content"
  }
}
```

or if it returns a collection:

```json
{
  "posts": [
    {
      "id": 1,
      "title": "Awesome Post Tile",
      "content": "Post content"
    },
    {
      "id": 2,
      "title": "Another Post Tile",
      "content": "Another post content"
    }
  ]
}
```
