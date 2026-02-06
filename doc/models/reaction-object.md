
# Reaction Object

*This model accepts additional fields of type Object.*

## Structure

`ReactionObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Count` | `int` | Required | - | int getCount() | setCount(int count) |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `Users` | `List<String>` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | List<String> getUsers() | setUsers(List<String> users) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "count": 186,
  "name": "name6",
  "users": [
    "users3",
    "users2"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

