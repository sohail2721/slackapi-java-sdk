
# Chat Update Success Schema

Schema for successful response of chat.update method

*This model accepts additional fields of type Object.*

## Structure

`ChatUpdateSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Channel` | `String` | Required | - | String getChannel() | setChannel(String channel) |
| `Message` | [`MessageObject1`](../../doc/models/message-object-1.md) | Required | - | MessageObject1 getMessage() | setMessage(MessageObject1 message) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Text` | `String` | Required | - | String getText() | setText(String text) |
| `Ts` | `String` | Required | - | String getTs() | setTs(String ts) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channel": "channel8",
  "message": {
    "attachments": [
      {
        "key1": "val1",
        "key2": "val2"
      },
      {
        "key1": "val1",
        "key2": "val2"
      }
    ],
    "blocks": {
      "key1": "val1",
      "key2": "val2"
    },
    "text": "text0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "ok": "True",
  "text": "text6",
  "ts": "ts8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

