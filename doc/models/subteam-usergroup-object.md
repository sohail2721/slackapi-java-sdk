
# Subteam Usergroup Object

*This model accepts additional fields of type Object.*

## Structure

`SubteamUsergroupObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AutoProvision` | `boolean` | Required | - | boolean getAutoProvision() | setAutoProvision(boolean autoProvision) |
| `AutoType` | `Object` | Required | - | Object getAutoType() | setAutoType(Object autoType) |
| `ChannelCount` | `Integer` | Optional | - | Integer getChannelCount() | setChannelCount(Integer channelCount) |
| `CreatedBy` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getCreatedBy() | setCreatedBy(String createdBy) |
| `DateCreate` | `int` | Required | - | int getDateCreate() | setDateCreate(int dateCreate) |
| `DateDelete` | `int` | Required | - | int getDateDelete() | setDateDelete(int dateDelete) |
| `DateUpdate` | `int` | Required | - | int getDateUpdate() | setDateUpdate(int dateUpdate) |
| `DeletedBy` | `Object` | Required | - | Object getDeletedBy() | setDeletedBy(Object deletedBy) |
| `Description` | `String` | Required | - | String getDescription() | setDescription(String description) |
| `EnterpriseSubteamId` | `String` | Required | - | String getEnterpriseSubteamId() | setEnterpriseSubteamId(String enterpriseSubteamId) |
| `Handle` | `String` | Required | - | String getHandle() | setHandle(String handle) |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^S[A-Z0-9]{2,}$` | String getId() | setId(String id) |
| `IsExternal` | `boolean` | Required | - | boolean getIsExternal() | setIsExternal(boolean isExternal) |
| `IsSubteam` | `boolean` | Required | - | boolean getIsSubteam() | setIsSubteam(boolean isSubteam) |
| `IsUsergroup` | `boolean` | Required | - | boolean getIsUsergroup() | setIsUsergroup(boolean isUsergroup) |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `Prefs` | [`Prefs`](../../doc/models/prefs.md) | Required | - | Prefs getPrefs() | setPrefs(Prefs prefs) |
| `TeamId` | `String` | Required | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` | String getTeamId() | setTeamId(String teamId) |
| `UpdatedBy` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getUpdatedBy() | setUpdatedBy(String updatedBy) |
| `UserCount` | `Integer` | Optional | - | Integer getUserCount() | setUserCount(Integer userCount) |
| `Users` | `List<String>` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | List<String> getUsers() | setUsers(List<String> users) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "auto_provision": false,
  "auto_type": {
    "key1": "val1",
    "key2": "val2"
  },
  "channel_count": 140,
  "created_by": "created_by4",
  "date_create": 240,
  "date_delete": 32,
  "date_update": 18,
  "deleted_by": {
    "key1": "val1",
    "key2": "val2"
  },
  "description": "description2",
  "enterprise_subteam_id": "enterprise_subteam_id6",
  "handle": "handle4",
  "id": "id8",
  "is_external": false,
  "is_subteam": false,
  "is_usergroup": false,
  "name": "name8",
  "prefs": {
    "channels": [
      "channels5",
      "channels4"
    ],
    "groups": [
      "groups4",
      "groups5",
      "groups6"
    ],
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "team_id": "team_id8",
  "updated_by": "updated_by2",
  "user_count": 110,
  "users": [
    "users5",
    "users4"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

