
# Icons 1

*This model accepts additional fields of type Object.*

## Structure

`Icons1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Emoji` | `String` | Optional | - | String getEmoji() | setEmoji(String emoji) |
| `Image64` | `String` | Optional | - | String getImage64() | setImage64(String image64) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "emoji": "emoji4",
  "image_64": "image_646",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

