
# Objs Team Profile Field

*This model accepts additional fields of type Object.*

## Structure

`ObjsTeamProfileField`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `FieldName` | `String` | Optional | - | String getFieldName() | setFieldName(String fieldName) |
| `Hint` | `String` | Required | - | String getHint() | setHint(String hint) |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^X[a-zA-Z0-9]{9,}$` | String getId() | setId(String id) |
| `IsHidden` | `Boolean` | Optional | - | Boolean getIsHidden() | setIsHidden(Boolean isHidden) |
| `Label` | `String` | Required | - | String getLabel() | setLabel(String label) |
| `Options` | `Object` | Optional | - | Object getOptions() | setOptions(Object options) |
| `Ordering` | `double` | Required | - | double getOrdering() | setOrdering(double ordering) |
| `PossibleValues` | `List<String>` | Optional | - | List<String> getPossibleValues() | setPossibleValues(List<String> possibleValues) |
| `Type` | [`Type`](../../doc/models/type.md) | Required | - | Type getType() | setType(Type type) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "field_name": "field_name4",
  "hint": "hint0",
  "id": "id0",
  "is_hidden": false,
  "label": "label0",
  "options": {
    "key1": "val1",
    "key2": "val2"
  },
  "ordering": 211.1,
  "possible_values": [
    "possible_values1",
    "possible_values2"
  ],
  "type": "options_list",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

