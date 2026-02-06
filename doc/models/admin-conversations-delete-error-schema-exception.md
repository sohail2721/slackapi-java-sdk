
# Admin Conversations Delete Error Schema Exception

Schema for error response from admin.conversations.delete

*This model accepts additional fields of type Object.*

## Structure

`AdminConversationsDeleteErrorSchemaException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Error` | [`Error3`](../../doc/models/error-3.md) | Required | - | Error3 getError() | setError(Error3 error) |
| `Ok` | `String` | Required, Constant | **Value**: `"False"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "error": "could_not_delete_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

