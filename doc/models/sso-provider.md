
# Sso Provider

*This model accepts additional fields of type Object.*

## Structure

`SsoProvider`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Label` | `String` | Optional | - | String getLabel() | setLabel(String label) |
| `Name` | `String` | Optional | - | String getName() | setName(String name) |
| `Type` | `String` | Optional | - | String getType() | setType(String type) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "label": "label6",
  "name": "name6",
  "type": "type6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

