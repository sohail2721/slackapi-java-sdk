
# Admin Conversations Disconnect Shared Error Schema Exception

Schema for error response from admin.conversations.disconnectShared

*This model accepts additional fields of type Object.*

## Structure

`AdminConversationsDisconnectSharedErrorSchemaException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Error` | [`Error4`](../../doc/models/error-4.md) | Required | - | Error4 getError() | setError(Error4 error) |
| `Ok` | `String` | Required, Constant | **Value**: `"False"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "error": "leaving_team_not_in_channel",
  "ok": "False",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

