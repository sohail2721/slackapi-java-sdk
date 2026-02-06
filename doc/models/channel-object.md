
# Channel Object

*This model accepts additional fields of type Object.*

## Structure

`ChannelObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AcceptedUser` | `String` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getAcceptedUser() | setAcceptedUser(String acceptedUser) |
| `Created` | `int` | Required | - | int getCreated() | setCreated(int created) |
| `Creator` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getCreator() | setCreator(String creator) |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` | String getId() | setId(String id) |
| `IsArchived` | `Boolean` | Optional | - | Boolean getIsArchived() | setIsArchived(Boolean isArchived) |
| `IsChannel` | `boolean` | Required | - | boolean getIsChannel() | setIsChannel(boolean isChannel) |
| `IsFrozen` | `Boolean` | Optional | - | Boolean getIsFrozen() | setIsFrozen(Boolean isFrozen) |
| `IsGeneral` | `Boolean` | Optional | - | Boolean getIsGeneral() | setIsGeneral(Boolean isGeneral) |
| `IsMember` | `Boolean` | Optional | - | Boolean getIsMember() | setIsMember(Boolean isMember) |
| `IsMoved` | `Integer` | Optional | - | Integer getIsMoved() | setIsMoved(Integer isMoved) |
| `IsMpim` | `boolean` | Required | - | boolean getIsMpim() | setIsMpim(boolean isMpim) |
| `IsNonThreadable` | `Boolean` | Optional | - | Boolean getIsNonThreadable() | setIsNonThreadable(Boolean isNonThreadable) |
| `IsOrgShared` | `boolean` | Required | - | boolean getIsOrgShared() | setIsOrgShared(boolean isOrgShared) |
| `IsPendingExtShared` | `Boolean` | Optional | - | Boolean getIsPendingExtShared() | setIsPendingExtShared(Boolean isPendingExtShared) |
| `IsPrivate` | `boolean` | Required | - | boolean getIsPrivate() | setIsPrivate(boolean isPrivate) |
| `IsReadOnly` | `Boolean` | Optional | - | Boolean getIsReadOnly() | setIsReadOnly(Boolean isReadOnly) |
| `IsShared` | `boolean` | Required | - | boolean getIsShared() | setIsShared(boolean isShared) |
| `IsThreadOnly` | `Boolean` | Optional | - | Boolean getIsThreadOnly() | setIsThreadOnly(Boolean isThreadOnly) |
| `LastRead` | `String` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` | String getLastRead() | setLastRead(String lastRead) |
| `Latest` | `Object` | Optional | - | Object getLatest() | setLatest(Object latest) |
| `Members` | `List<String>` | Required | **Constraints**: *Minimum Items*: `0`, *Unique Items Required*, *Pattern*: `^[UW][A-Z0-9]{2,}$` | List<String> getMembers() | setMembers(List<String> members) |
| `Name` | `String` | Required | - | String getName() | setName(String name) |
| `NameNormalized` | `String` | Required | - | String getNameNormalized() | setNameNormalized(String nameNormalized) |
| `NumMembers` | `Integer` | Optional | - | Integer getNumMembers() | setNumMembers(Integer numMembers) |
| `PendingShared` | `List<String>` | Optional | **Constraints**: *Minimum Items*: `0`, *Unique Items Required*, *Pattern*: `^[T][A-Z0-9]{2,}$` | List<String> getPendingShared() | setPendingShared(List<String> pendingShared) |
| `PreviousNames` | `List<String>` | Optional | **Constraints**: *Minimum Items*: `0`, *Unique Items Required* | List<String> getPreviousNames() | setPreviousNames(List<String> previousNames) |
| `Priority` | `Double` | Optional | - | Double getPriority() | setPriority(Double priority) |
| `Purpose` | [`Purpose`](../../doc/models/purpose.md) | Required | - | Purpose getPurpose() | setPurpose(Purpose purpose) |
| `Topic` | [`Topic`](../../doc/models/topic.md) | Required | - | Topic getTopic() | setTopic(Topic topic) |
| `Unlinked` | `Integer` | Optional | - | Integer getUnlinked() | setUnlinked(Integer unlinked) |
| `UnreadCount` | `Integer` | Optional | - | Integer getUnreadCount() | setUnreadCount(Integer unreadCount) |
| `UnreadCountDisplay` | `Integer` | Optional | - | Integer getUnreadCountDisplay() | setUnreadCountDisplay(Integer unreadCountDisplay) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "accepted_user": "accepted_user4",
  "created": 68,
  "creator": "creator4",
  "id": "id6",
  "is_archived": false,
  "is_channel": false,
  "is_frozen": false,
  "is_general": false,
  "is_member": false,
  "is_mpim": false,
  "is_org_shared": false,
  "is_private": false,
  "is_shared": false,
  "members": [
    "members4",
    "members5",
    "members6"
  ],
  "name": "name6",
  "name_normalized": "name_normalized4",
  "purpose": {
    "creator": "creator4",
    "last_set": 30,
    "value": "value8",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "topic": {
    "creator": "creator6",
    "last_set": 242,
    "value": "value0",
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

