
# Objs Team Profile Field Option

*This model accepts additional fields of type Object.*

## Structure

`ObjsTeamProfileFieldOption`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `IsCustom` | `Boolean` | Optional | - | Boolean getIsCustom() | setIsCustom(Boolean isCustom) |
| `IsMultipleEntry` | `Boolean` | Optional | - | Boolean getIsMultipleEntry() | setIsMultipleEntry(Boolean isMultipleEntry) |
| `IsProtected` | `Boolean` | Optional | - | Boolean getIsProtected() | setIsProtected(Boolean isProtected) |
| `IsScim` | `Boolean` | Optional | - | Boolean getIsScim() | setIsScim(Boolean isScim) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "is_custom": false,
  "is_multiple_entry": false,
  "is_protected": false,
  "is_scim": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

