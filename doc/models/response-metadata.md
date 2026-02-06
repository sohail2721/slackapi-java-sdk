
# Response Metadata

*This model accepts additional fields of type Object.*

## Structure

`ResponseMetadata`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `NextCursor` | `String` | Required | - | String getNextCursor() | setNextCursor(String nextCursor) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "next_cursor": "next_cursor0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

