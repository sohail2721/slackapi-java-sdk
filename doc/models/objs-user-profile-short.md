
# Objs User Profile Short

*This model accepts additional fields of type Object.*

## Structure

`ObjsUserProfileShort`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AvatarHash` | `String` | Required | - | String getAvatarHash() | setAvatarHash(String avatarHash) |
| `DisplayName` | `String` | Required | - | String getDisplayName() | setDisplayName(String displayName) |
| `DisplayNameNormalized` | `String` | Optional | - | String getDisplayNameNormalized() | setDisplayNameNormalized(String displayNameNormalized) |
| `FirstName` | `String` | Required | - | String getFirstName() | setFirstName(String firstName) |
| `Image72` | `String` | Required | - | String getImage72() | setImage72(String image72) |
| `IsRestricted` | `boolean` | Required | - | boolean getIsRestricted() | setIsRestricted(boolean isRestricted) |
| `IsUltraRestricted` | `boolean` | Required | - | boolean getIsUltraRestricted() | setIsUltraRestricted(boolean isUltraRestricted) |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `RealName` | `String` | Required | - | String getRealName() | setRealName(String realName) |
| `RealNameNormalized` | `String` | Optional | - | String getRealNameNormalized() | setRealNameNormalized(String realNameNormalized) |
| `Team` | `String` | Required | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` | String getTeam() | setTeam(String team) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "avatar_hash": "avatar_hash2",
  "display_name": "display_name2",
  "display_name_normalized": "display_name_normalized2",
  "first_name": "first_name2",
  "image_72": "image_726",
  "is_restricted": false,
  "is_ultra_restricted": false,
  "name": "name2",
  "real_name": "real_name8",
  "real_name_normalized": "real_name_normalized4",
  "team": "team8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

