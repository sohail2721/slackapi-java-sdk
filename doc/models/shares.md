
# Shares

*This model accepts additional fields of type Object.*

## Structure

`Shares`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Private` | `Object` | Optional | - | Object getPrivate() | setPrivate(Object mPrivate) |
| `Public` | `Object` | Optional | - | Object getPublic() | setPublic(Object mPublic) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "private": {
    "key1": "val1",
    "key2": "val2"
  },
  "public": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

