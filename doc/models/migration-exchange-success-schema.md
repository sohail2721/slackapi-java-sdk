
# Migration Exchange Success Schema

Schema for successful response from migration.exchange method

*This model accepts additional fields of type Object.*

## Structure

`MigrationExchangeSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `EnterpriseId` | `String` | Required | - | String getEnterpriseId() | setEnterpriseId(String enterpriseId) |
| `InvalidUserIds` | `List<String>` | Optional | - | List<String> getInvalidUserIds() | setInvalidUserIds(List<String> invalidUserIds) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `TeamId` | `String` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` | String getTeamId() | setTeamId(String teamId) |
| `UserIdMap` | `Object` | Optional | - | Object getUserIdMap() | setUserIdMap(Object userIdMap) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "enterprise_id": "enterprise_id8",
  "ok": "True",
  "team_id": "team_id8",
  "invalid_user_ids": [
    "invalid_user_ids6"
  ],
  "user_id_map": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

