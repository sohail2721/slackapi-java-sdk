
# Conversations Leave Success Schema

Schema for successful response from conversations.leave method

*This model accepts additional fields of type Object.*

## Structure

`ConversationsLeaveSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `NotInChannel` | `Boolean` | Optional | - | Boolean getNotInChannel() | setNotInChannel(Boolean notInChannel) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "not_in_channel": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

