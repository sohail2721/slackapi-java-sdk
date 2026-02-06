
# Users Conversations Success Schema

Schema for successful response from users.conversations method. Returned conversation objects do not include `num_members` or `is_member`

*This model accepts additional fields of type Object.*

## Structure

`UsersConversationsSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Channels` | `List<Object>` | Required | **Constraints**: *Unique Items Required* | List<Object> getChannels() | setChannels(List<Object> channels) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `ResponseMetadata` | [`ResponseMetadata`](../../doc/models/response-metadata.md) | Optional | - | ResponseMetadata getResponseMetadata() | setResponseMetadata(ResponseMetadata responseMetadata) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channels": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ok": "True",
  "response_metadata": {
    "next_cursor": "next_cursor2",
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

