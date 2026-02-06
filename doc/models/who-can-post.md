
# Who Can Post

*This model accepts additional fields of type Object.*

## Structure

`WhoCanPost`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Type` | `List<String>` | Optional | - | List<String> getType() | setType(List<String> type) |
| `User` | `List<String>` | Optional | - | List<String> getUser() | setUser(List<String> user) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "type": [
    "type7",
    "type8"
  ],
  "user": [
    "user8",
    "user9"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

