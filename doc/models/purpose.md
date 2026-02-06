
# Purpose

*This model accepts additional fields of type Object.*

## Structure

`Purpose`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Creator` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{8,}$\|^$` | String getCreator() | setCreator(String creator) |
| `LastSet` | `int` | Required | - | int getLastSet() | setLastSet(int lastSet) |
| `Value` | `String` | Required | - | String getValue() | setValue(String value) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "creator": "creator6",
  "last_set": 108,
  "value": "value0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

