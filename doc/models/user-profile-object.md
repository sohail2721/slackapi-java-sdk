
# User Profile Object

*This model accepts additional fields of type Object.*

## Structure

`UserProfileObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AlwaysActive` | `Boolean` | Optional | - | Boolean getAlwaysActive() | setAlwaysActive(Boolean alwaysActive) |
| `ApiAppId` | `String` | Optional | **Constraints**: *Pattern*: `^(A[A-Z0-9]{1,})?$` | String getApiAppId() | setApiAppId(String apiAppId) |
| `AvatarHash` | `String` | Required | - | String getAvatarHash() | setAvatarHash(String avatarHash) |
| `BotId` | `String` | Optional | **Constraints**: *Pattern*: `^B[A-Z0-9]{8,}$` | String getBotId() | setBotId(String botId) |
| `DisplayName` | `String` | Required | - | String getDisplayName() | setDisplayName(String displayName) |
| `DisplayNameNormalized` | `String` | Required | - | String getDisplayNameNormalized() | setDisplayNameNormalized(String displayNameNormalized) |
| `Email` | `String` | Optional | - | String getEmail() | setEmail(String email) |
| `Fields` | `List<Object>` | Required | - | List<Object> getFields() | setFields(List<Object> fields) |
| `FirstName` | `String` | Optional | - | String getFirstName() | setFirstName(String firstName) |
| `GuestExpirationTs` | `Integer` | Optional | - | Integer getGuestExpirationTs() | setGuestExpirationTs(Integer guestExpirationTs) |
| `GuestInvitedBy` | `String` | Optional | - | String getGuestInvitedBy() | setGuestInvitedBy(String guestInvitedBy) |
| `Image1024` | `String` | Optional | - | String getImage1024() | setImage1024(String image1024) |
| `Image192` | `String` | Optional | - | String getImage192() | setImage192(String image192) |
| `Image24` | `String` | Optional | - | String getImage24() | setImage24(String image24) |
| `Image32` | `String` | Optional | - | String getImage32() | setImage32(String image32) |
| `Image48` | `String` | Optional | - | String getImage48() | setImage48(String image48) |
| `Image512` | `String` | Optional | - | String getImage512() | setImage512(String image512) |
| `Image72` | `String` | Optional | - | String getImage72() | setImage72(String image72) |
| `ImageOriginal` | `String` | Optional | - | String getImageOriginal() | setImageOriginal(String imageOriginal) |
| `IsAppUser` | `Boolean` | Optional | - | Boolean getIsAppUser() | setIsAppUser(Boolean isAppUser) |
| `IsCustomImage` | `Boolean` | Optional | - | Boolean getIsCustomImage() | setIsCustomImage(Boolean isCustomImage) |
| `IsRestricted` | `Boolean` | Optional | - | Boolean getIsRestricted() | setIsRestricted(Boolean isRestricted) |
| `IsUltraRestricted` | `Boolean` | Optional | - | Boolean getIsUltraRestricted() | setIsUltraRestricted(Boolean isUltraRestricted) |
| `LastAvatarImageHash` | `String` | Optional | - | String getLastAvatarImageHash() | setLastAvatarImageHash(String lastAvatarImageHash) |
| `LastName` | `String` | Optional | - | String getLastName() | setLastName(String lastName) |
| `MembershipsCount` | `Integer` | Optional | - | Integer getMembershipsCount() | setMembershipsCount(Integer membershipsCount) |
| `Name` | `String` | Optional | - | String getName() | setName(String name) |
| `Phone` | `String` | Required | - | String getPhone() | setPhone(String phone) |
| `Pronouns` | `String` | Optional | - | String getPronouns() | setPronouns(String pronouns) |
| `RealName` | `String` | Required | - | String getRealName() | setRealName(String realName) |
| `RealNameNormalized` | `String` | Required | - | String getRealNameNormalized() | setRealNameNormalized(String realNameNormalized) |
| `Skype` | `String` | Required | - | String getSkype() | setSkype(String skype) |
| `StatusDefaultEmoji` | `String` | Optional | - | String getStatusDefaultEmoji() | setStatusDefaultEmoji(String statusDefaultEmoji) |
| `StatusDefaultText` | `String` | Optional | - | String getStatusDefaultText() | setStatusDefaultText(String statusDefaultText) |
| `StatusDefaultTextCanonical` | `String` | Optional | - | String getStatusDefaultTextCanonical() | setStatusDefaultTextCanonical(String statusDefaultTextCanonical) |
| `StatusEmoji` | `String` | Required | - | String getStatusEmoji() | setStatusEmoji(String statusEmoji) |
| `StatusExpiration` | `Integer` | Optional | - | Integer getStatusExpiration() | setStatusExpiration(Integer statusExpiration) |
| `StatusText` | `String` | Required | - | String getStatusText() | setStatusText(String statusText) |
| `StatusTextCanonical` | `String` | Optional | - | String getStatusTextCanonical() | setStatusTextCanonical(String statusTextCanonical) |
| `Team` | `String` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` | String getTeam() | setTeam(String team) |
| `Title` | `String` | Required | - | String getTitle() | setTitle(String title) |
| `Updated` | `Integer` | Optional | - | Integer getUpdated() | setUpdated(Integer updated) |
| `UserId` | `String` | Optional | - | String getUserId() | setUserId(String userId) |
| `Username` | `String` | Optional | - | String getUsername() | setUsername(String username) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "always_active": false,
  "api_app_id": "api_app_id8",
  "avatar_hash": "avatar_hash8",
  "bot_id": "bot_id8",
  "display_name": "display_name8",
  "display_name_normalized": "display_name_normalized8",
  "email": "email8",
  "fields": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "first_name": "first_name8",
  "phone": "phone2",
  "real_name": "real_name6",
  "real_name_normalized": "real_name_normalized8",
  "skype": "skype8",
  "status_emoji": "status_emoji2",
  "status_text": "status_text0",
  "title": "title4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

