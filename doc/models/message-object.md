
# Message Object

*This model accepts additional fields of type Object.*

## Structure

`MessageObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Attachments` | [`List<Attachment>`](../../doc/models/attachment.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* | List<Attachment> getAttachments() | setAttachments(List<Attachment> attachments) |
| `Blocks` | [`List<BlockKitBlock>`](../../doc/models/block-kit-block.md) | Optional | This is a very loose definition, in the future, we'll populate this with deeper schema in this definition namespace. | List<BlockKitBlock> getBlocks() | setBlocks(List<BlockKitBlock> blocks) |
| `BotId` | `Object` | Optional | - | Object getBotId() | setBotId(Object botId) |
| `BotProfile` | [`BotProfileObject`](../../doc/models/bot-profile-object.md) | Optional | - | BotProfileObject getBotProfile() | setBotProfile(BotProfileObject botProfile) |
| `ClientMsgId` | `String` | Optional | - | String getClientMsgId() | setClientMsgId(String clientMsgId) |
| `Comment` | [`FileCommentObject`](../../doc/models/file-comment-object.md) | Optional | - | FileCommentObject getComment() | setComment(FileCommentObject comment) |
| `DisplayAsBot` | `Boolean` | Optional | - | Boolean getDisplayAsBot() | setDisplayAsBot(Boolean displayAsBot) |
| `File` | [`FileObject`](../../doc/models/file-object.md) | Optional | - | FileObject getFile() | setFile(FileObject file) |
| `Files` | [`List<FileObject>`](../../doc/models/file-object.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* | List<FileObject> getFiles() | setFiles(List<FileObject> files) |
| `Icons` | [`Icons1`](../../doc/models/icons-1.md) | Optional | - | Icons1 getIcons() | setIcons(Icons1 icons) |
| `Inviter` | `String` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getInviter() | setInviter(String inviter) |
| `IsDelayedMessage` | `Boolean` | Optional | - | Boolean getIsDelayedMessage() | setIsDelayedMessage(Boolean isDelayedMessage) |
| `IsIntro` | `Boolean` | Optional | - | Boolean getIsIntro() | setIsIntro(Boolean isIntro) |
| `IsStarred` | `Boolean` | Optional | - | Boolean getIsStarred() | setIsStarred(Boolean isStarred) |
| `LastRead` | `String` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` | String getLastRead() | setLastRead(String lastRead) |
| `LatestReply` | `String` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` | String getLatestReply() | setLatestReply(String latestReply) |
| `Name` | `String` | Optional | - | String getName() | setName(String name) |
| `OldName` | `String` | Optional | - | String getOldName() | setOldName(String oldName) |
| `ParentUserId` | `String` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getParentUserId() | setParentUserId(String parentUserId) |
| `Permalink` | `String` | Optional | - | String getPermalink() | setPermalink(String permalink) |
| `PinnedTo` | `List<String>` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` | List<String> getPinnedTo() | setPinnedTo(List<String> pinnedTo) |
| `Purpose` | `String` | Optional | - | String getPurpose() | setPurpose(String purpose) |
| `Reactions` | [`List<ReactionObject>`](../../doc/models/reaction-object.md) | Optional | - | List<ReactionObject> getReactions() | setReactions(List<ReactionObject> reactions) |
| `ReplyCount` | `Integer` | Optional | - | Integer getReplyCount() | setReplyCount(Integer replyCount) |
| `ReplyUsers` | `List<String>` | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required*, *Pattern*: `^[UW][A-Z0-9]{2,}$` | List<String> getReplyUsers() | setReplyUsers(List<String> replyUsers) |
| `ReplyUsersCount` | `Integer` | Optional | - | Integer getReplyUsersCount() | setReplyUsersCount(Integer replyUsersCount) |
| `SourceTeam` | `String` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` | String getSourceTeam() | setSourceTeam(String sourceTeam) |
| `Subscribed` | `Boolean` | Optional | - | Boolean getSubscribed() | setSubscribed(Boolean subscribed) |
| `Subtype` | `String` | Optional | - | String getSubtype() | setSubtype(String subtype) |
| `Team` | `String` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` | String getTeam() | setTeam(String team) |
| `Text` | `String` | Required | - | String getText() | setText(String text) |
| `ThreadTs` | `String` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` | String getThreadTs() | setThreadTs(String threadTs) |
| `Topic` | `String` | Optional | - | String getTopic() | setTopic(String topic) |
| `Ts` | `String` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` | String getTs() | setTs(String ts) |
| `Type` | `String` | Required | - | String getType() | setType(String type) |
| `UnreadCount` | `Integer` | Optional | - | Integer getUnreadCount() | setUnreadCount(Integer unreadCount) |
| `Upload` | `Boolean` | Optional | - | Boolean getUpload() | setUpload(Boolean upload) |
| `User` | `String` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getUser() | setUser(String user) |
| `UserProfile` | [`ObjsUserProfileShort`](../../doc/models/objs-user-profile-short.md) | Optional | - | ObjsUserProfileShort getUserProfile() | setUserProfile(ObjsUserProfileShort userProfile) |
| `UserTeam` | `String` | Optional | **Constraints**: *Pattern*: `^[TE][A-Z0-9]{8,}$` | String getUserTeam() | setUserTeam(String userTeam) |
| `Username` | `String` | Optional | - | String getUsername() | setUsername(String username) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "attachments": [
    {
      "fallback": "fallback4",
      "id": 36,
      "image_bytes": 34,
      "image_height": 154,
      "image_url": "image_url6",
      "image_width": 24,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "fallback": "fallback4",
      "id": 36,
      "image_bytes": 34,
      "image_height": 154,
      "image_url": "image_url6",
      "image_width": 24,
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "blocks": [
    {
      "type": "type4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "type": "type4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "bot_id": {
    "key1": "val1",
    "key2": "val2"
  },
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
  "client_msg_id": "client_msg_id4",
  "text": "text8",
  "ts": "ts0",
  "type": "type8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

