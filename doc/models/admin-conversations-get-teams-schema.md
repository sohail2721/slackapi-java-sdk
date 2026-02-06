
# Admin Conversations Get Teams Schema

Schema for successful response of admin.conversations.getTeams

*This model accepts additional fields of type Object.*

## Structure

`AdminConversationsGetTeamsSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `ResponseMetadata` | [`ResponseMetadata`](../../doc/models/response-metadata.md) | Optional | - | ResponseMetadata getResponseMetadata() | setResponseMetadata(ResponseMetadata responseMetadata) |
| `TeamIds` | `List<String>` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` | List<String> getTeamIds() | setTeamIds(List<String> teamIds) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "team_ids": [
    "team_ids9",
    "team_ids0"
  ],
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

