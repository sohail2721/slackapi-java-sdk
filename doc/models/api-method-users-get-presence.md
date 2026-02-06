
# Api Method Users Get Presence

Generated from users.getPresence with shasum e7251aec575d8863f9e0eb38663ae9dc26655f65

*This model accepts additional fields of type Object.*

## Structure

`ApiMethodUsersGetPresence`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AutoAway` | `Boolean` | Optional | - | Boolean getAutoAway() | setAutoAway(Boolean autoAway) |
| `ConnectionCount` | `Integer` | Optional | - | Integer getConnectionCount() | setConnectionCount(Integer connectionCount) |
| `LastActivity` | `Integer` | Optional | - | Integer getLastActivity() | setLastActivity(Integer lastActivity) |
| `ManualAway` | `Boolean` | Optional | - | Boolean getManualAway() | setManualAway(Boolean manualAway) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Online` | `Boolean` | Optional | - | Boolean getOnline() | setOnline(Boolean online) |
| `Presence` | `String` | Required | - | String getPresence() | setPresence(String presence) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "presence": "presence8",
  "auto_away": false,
  "connection_count": 42,
  "last_activity": 166,
  "manual_away": false,
  "online": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

