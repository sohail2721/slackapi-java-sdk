
# Auth Test Success Schema

Schema for successful response auth.test method

*This model accepts additional fields of type Object.*

## Structure

`AuthTestSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `BotId` | `String` | Optional | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` | String getBotId() | setBotId(String botId) |
| `IsEnterpriseInstall` | `Boolean` | Optional | - | Boolean getIsEnterpriseInstall() | setIsEnterpriseInstall(Boolean isEnterpriseInstall) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Team` | `String` | Required | - | String getTeam() | setTeam(String team) |
| `TeamId` | `String` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` | String getTeamId() | setTeamId(String teamId) |
| `Url` | `String` | Required | - | String getUrl() | setUrl(String url) |
| `User` | `String` | Required | - | String getUser() | setUser(String user) |
| `UserId` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getUserId() | setUserId(String userId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "team": "team0",
  "team_id": "team_id4",
  "url": "url4",
  "user": "user0",
  "user_id": "user_id8",
  "bot_id": "bot_id6",
  "is_enterprise_install": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

