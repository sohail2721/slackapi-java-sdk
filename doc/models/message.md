
# Message

*This model accepts additional fields of type Object.*

## Structure

`Message`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `BotId` | `String` | Required | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` | String getBotId() | setBotId(String botId) |
| `BotProfile` | [`BotProfileObject`](../../doc/models/bot-profile-object.md) | Optional | - | BotProfileObject getBotProfile() | setBotProfile(BotProfileObject botProfile) |
| `Team` | `String` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` | String getTeam() | setTeam(String team) |
| `Text` | `String` | Required | - | String getText() | setText(String text) |
| `Type` | `String` | Required | - | String getType() | setType(String type) |
| `User` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getUser() | setUser(String user) |
| `Username` | `String` | Optional | - | String getUsername() | setUsername(String username) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "bot_id": "bot_id0",
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
  "team": "team4",
  "text": "text4",
  "type": "type4",
  "user": "user6",
  "username": "username4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

