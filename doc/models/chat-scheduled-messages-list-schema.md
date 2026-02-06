
# Chat Scheduled Messages List Schema

Schema for successful response from chat.scheduledMessages.list method

*This model accepts additional fields of type Object.*

## Structure

`ChatScheduledMessagesListSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `ResponseMetadata` | [`ResponseMetadata`](../../doc/models/response-metadata.md) | Required | - | ResponseMetadata getResponseMetadata() | setResponseMetadata(ResponseMetadata responseMetadata) |
| `ScheduledMessages` | [`List<ScheduledMessage>`](../../doc/models/scheduled-message.md) | Required | - | List<ScheduledMessage> getScheduledMessages() | setScheduledMessages(List<ScheduledMessage> scheduledMessages) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "response_metadata": {
    "next_cursor": "next_cursor2",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "scheduled_messages": [
    {
      "channel_id": "channel_id8",
      "date_created": 100,
      "id": "id2",
      "post_at": 0,
      "text": "text2",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

