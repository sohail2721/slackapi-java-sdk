
# Conversations Open Success Schema

Schema for successful response from conversations.open method when opening channels, ims, mpims

*This model accepts additional fields of type Object.*

## Structure

`ConversationsOpenSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AlreadyOpen` | `Boolean` | Optional | - | Boolean getAlreadyOpen() | setAlreadyOpen(Boolean alreadyOpen) |
| `Channel` | `Object` | Required | - | Object getChannel() | setChannel(Object channel) |
| `NoOp` | `Boolean` | Optional | - | Boolean getNoOp() | setNoOp(Boolean noOp) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channel": {
    "key1": "val1",
    "key2": "val2"
  },
  "ok": "True",
  "already_open": false,
  "no_op": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

