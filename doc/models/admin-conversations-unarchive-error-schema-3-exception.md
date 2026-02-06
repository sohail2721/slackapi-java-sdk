
# Admin Conversations Unarchive Error Schema 3 Exception

Schema for error response from admin.conversations.unarchive

*This model accepts additional fields of type Object.*

## Structure

`AdminConversationsUnarchiveErrorSchema3Exception`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Error` | [`Error11`](../../doc/models/error-11.md) | Required | - | Error11 getError() | setError(Error11 error) |
| `Ok` | `String` | Required, Constant | **Value**: `"False"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "error": "restricted_action",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

