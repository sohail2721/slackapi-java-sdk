
# Bot Profile Object

*This model accepts additional fields of type Object.*

## Structure

`BotProfileObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AppId` | `String` | Required | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` | String getAppId() | setAppId(String appId) |
| `Deleted` | `boolean` | Required | - | boolean getDeleted() | setDeleted(boolean deleted) |
| `Icons` | [`Icons`](../../doc/models/icons.md) | Required | - | Icons getIcons() | setIcons(Icons icons) |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` | String getId() | setId(String id) |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `TeamId` | `String` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` | String getTeamId() | setTeamId(String teamId) |
| `Updated` | `int` | Required | - | int getUpdated() | setUpdated(int updated) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "app_id": "app_id4",
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
  "id": "id2",
  "name": "name2",
  "team_id": "team_id6",
  "updated": 94,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

