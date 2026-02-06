
# Chat Schedule Message Success Schema

Schema for successful response of chat.scheduleMessage method

*This model accepts additional fields of type Object.*

## Structure

`ChatScheduleMessageSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Channel` | `String` | Required | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` | String getChannel() | setChannel(String channel) |
| `Message` | [`Message`](../../doc/models/message.md) | Required | - | Message getMessage() | setMessage(Message message) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `PostAt` | `int` | Required | - | int getPostAt() | setPostAt(int postAt) |
| `ScheduledMessageId` | `String` | Required | **Constraints**: *Pattern*: `^[Q][A-Z0-9]{8,}$` | String getScheduledMessageId() | setScheduledMessageId(String scheduledMessageId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channel": "channel4",
  "message": {
    "bot_id": "bot_id6",
    "bot_profile": {
      "app_id": "app_id8",
      "deleted": false,
      "icons": {
        "image_36": "image_362",
        "image_48": "image_488",
        "image_72": "image_722",
        "exampleAdditionalProperty": {
          "key1": "val1",
          "key2": "val2"
        }
      },
      "id": "id8",
      "name": "name8",
      "team_id": "team_id8",
      "updated": 44,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "team": "team0",
    "text": "text0",
    "type": "type0",
    "user": "user0",
    "username": "username0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "ok": "True",
  "post_at": 128,
  "scheduled_message_id": "scheduled_message_id2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

