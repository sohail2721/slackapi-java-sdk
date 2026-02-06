
# Self

*This model accepts additional fields of type Object.*

## Structure

`Self`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getId() | setId(String id) |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "id": "id6",
  "name": "name6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

