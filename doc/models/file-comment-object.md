
# File Comment Object

*This model accepts additional fields of type Object.*

## Structure

`FileCommentObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Comment` | `String` | Required | - | String getComment() | setComment(String comment) |
| `Created` | `int` | Required | - | int getCreated() | setCreated(int created) |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^Fc[A-Z0-9]{8,}$` | String getId() | setId(String id) |
| `IsIntro` | `boolean` | Required | - | boolean getIsIntro() | setIsIntro(boolean isIntro) |
| `IsStarred` | `Boolean` | Optional | - | Boolean getIsStarred() | setIsStarred(Boolean isStarred) |
| `NumStars` | `Integer` | Optional | - | Integer getNumStars() | setNumStars(Integer numStars) |
| `PinnedInfo` | `Object` | Optional | - | Object getPinnedInfo() | setPinnedInfo(Object pinnedInfo) |
| `PinnedTo` | `List<String>` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` | List<String> getPinnedTo() | setPinnedTo(List<String> pinnedTo) |
| `Reactions` | [`List<ReactionObject>`](../../doc/models/reaction-object.md) | Optional | - | List<ReactionObject> getReactions() | setReactions(List<ReactionObject> reactions) |
| `Timestamp` | `int` | Required | - | int getTimestamp() | setTimestamp(int timestamp) |
| `User` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getUser() | setUser(String user) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "comment": "comment2",
  "created": 212,
  "id": "id4",
  "is_intro": false,
  "is_starred": false,
  "num_stars": 180,
  "pinned_info": {
    "key1": "val1",
    "key2": "val2"
  },
  "pinned_to": [
    "pinned_to8",
    "pinned_to9"
  ],
  "reactions": [
    {
      "count": 208,
      "name": "name8",
      "users": [
        "users5",
        "users6",
        "users7"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "count": 208,
      "name": "name8",
      "users": [
        "users5",
        "users6",
        "users7"
      ],
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "timestamp": 66,
  "user": "user4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

