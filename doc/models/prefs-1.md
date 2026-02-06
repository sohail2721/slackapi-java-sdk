
# Prefs 1

*This model accepts additional fields of type Object.*

## Structure

`Prefs1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `CanThread` | [`CanThread`](../../doc/models/can-thread.md) | Optional | - | CanThread getCanThread() | setCanThread(CanThread canThread) |
| `WhoCanPost` | [`WhoCanPost`](../../doc/models/who-can-post.md) | Optional | - | WhoCanPost getWhoCanPost() | setWhoCanPost(WhoCanPost whoCanPost) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "can_thread": {
    "type": [
      "type1",
      "type0"
    ],
    "user": [
      "user6",
      "user7"
    ],
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "who_can_post": {
    "type": [
      "type5",
      "type4"
    ],
    "user": [
      "user0",
      "user1"
    ],
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

