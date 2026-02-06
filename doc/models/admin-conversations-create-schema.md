
# Admin Conversations Create Schema

Schema for successful response of admin.conversations.create

*This model accepts additional fields of type Object.*

## Structure

`AdminConversationsCreateSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ChannelId` | `String` | Optional | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` | String getChannelId() | setChannelId(String channelId) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "channel_id": "channel_id6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

