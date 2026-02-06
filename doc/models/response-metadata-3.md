
# Response Metadata 3

*This model accepts additional fields of type Object.*

## Structure

`ResponseMetadata3`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Warnings` | `List<String>` | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* | List<String> getWarnings() | setWarnings(List<String> warnings) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "warnings": [
    "warnings4",
    "warnings5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

