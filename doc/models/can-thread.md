
# Can Thread

*This model accepts additional fields of type Object.*

## Structure

`CanThread`

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
    "type7"
  ],
  "user": [
    "user2",
    "user3",
    "user4"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

