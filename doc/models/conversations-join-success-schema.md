
# Conversations Join Success Schema

Schema for successful response from conversations.join method

*This model accepts additional fields of type Object.*

## Structure

`ConversationsJoinSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Channel` | `Object` | Required | - | Object getChannel() | setChannel(Object channel) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `ResponseMetadata` | [`ResponseMetadata3`](../../doc/models/response-metadata-3.md) | Optional | - | ResponseMetadata3 getResponseMetadata() | setResponseMetadata(ResponseMetadata3 responseMetadata) |
| `Warning` | `String` | Optional | - | String getWarning() | setWarning(String warning) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channel": {
    "key1": "val1",
    "key2": "val2"
  },
  "ok": "True",
  "response_metadata": {
    "warnings": [
      "warnings8",
      "warnings9",
      "warnings0"
    ],
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "warning": "warning4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

