
# Conversations Replies Success Schema

Schema for successful response from conversations.replies method

*This model accepts additional fields of type Object.*

## Structure

`ConversationsRepliesSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `HasMore` | `Boolean` | Optional | - | Boolean getHasMore() | setHasMore(Boolean hasMore) |
| `Messages` | `List<Object>` | Required | - | List<Object> getMessages() | setMessages(List<Object> messages) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "messages": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ok": "True",
  "has_more": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

