
# Admin Conversations Get Conversation Prefs Schema

Schema for successful response of admin.conversations.getConversationPrefs

*This model accepts additional fields of type Object.*

## Structure

`AdminConversationsGetConversationPrefsSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Prefs` | [`Prefs1`](../../doc/models/prefs-1.md) | Optional | - | Prefs1 getPrefs() | setPrefs(Prefs1 prefs) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "prefs": {
    "can_thread": {
      "type": [
        "type1",
        "type0"
      ],
      "user": [
        "user6",
        "user7"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "who_can_post": {
      "type": [
        "type5",
        "type4"
      ],
      "user": [
        "user0",
        "user1"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

