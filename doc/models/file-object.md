
# File Object

*This model accepts additional fields of type Object.*

## Structure

`FileObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Channels` | `List<String>` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[C][A-Z0-9]{2,}$` | List<String> getChannels() | setChannels(List<String> channels) |
| `CommentsCount` | `Integer` | Optional | - | Integer getCommentsCount() | setCommentsCount(Integer commentsCount) |
| `Created` | `Integer` | Optional | - | Integer getCreated() | setCreated(Integer created) |
| `DateDelete` | `Integer` | Optional | - | Integer getDateDelete() | setDateDelete(Integer dateDelete) |
| `DisplayAsBot` | `Boolean` | Optional | - | Boolean getDisplayAsBot() | setDisplayAsBot(Boolean displayAsBot) |
| `Editable` | `Boolean` | Optional | - | Boolean getEditable() | setEditable(Boolean editable) |
| `Editor` | `String` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getEditor() | setEditor(String editor) |
| `ExternalId` | `String` | Optional | - | String getExternalId() | setExternalId(String externalId) |
| `ExternalType` | `String` | Optional | - | String getExternalType() | setExternalType(String externalType) |
| `ExternalUrl` | `String` | Optional | - | String getExternalUrl() | setExternalUrl(String externalUrl) |
| `Filetype` | `String` | Optional | - | String getFiletype() | setFiletype(String filetype) |
| `Groups` | `List<String>` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[G][A-Z0-9]{8,}$` | List<String> getGroups() | setGroups(List<String> groups) |
| `HasRichPreview` | `Boolean` | Optional | - | Boolean getHasRichPreview() | setHasRichPreview(Boolean hasRichPreview) |
| `Id` | `String` | Optional | **Constraints**: *Pattern*: `^[F][A-Z0-9]{8,}$` | String getId() | setId(String id) |
| `ImageExifRotation` | `Integer` | Optional | - | Integer getImageExifRotation() | setImageExifRotation(Integer imageExifRotation) |
| `Ims` | `List<String>` | Optional | **Constraints**: *Unique Items Required*, *Pattern*: `^[D][A-Z0-9]{8,}$` | List<String> getIms() | setIms(List<String> ims) |
| `IsExternal` | `Boolean` | Optional | - | Boolean getIsExternal() | setIsExternal(Boolean isExternal) |
| `IsPublic` | `Boolean` | Optional | - | Boolean getIsPublic() | setIsPublic(Boolean isPublic) |
| `IsStarred` | `Boolean` | Optional | - | Boolean getIsStarred() | setIsStarred(Boolean isStarred) |
| `IsTombstoned` | `Boolean` | Optional | - | Boolean getIsTombstoned() | setIsTombstoned(Boolean isTombstoned) |
| `LastEditor` | `String` | Optional | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getLastEditor() | setLastEditor(String lastEditor) |
| `Mimetype` | `String` | Optional | - | String getMimetype() | setMimetype(String mimetype) |
| `Mode` | `String` | Optional | - | String getMode() | setMode(String mode) |
| `Name` | `String` | Optional | - | String getName() | setName(String name) |
| `NonOwnerEditable` | `Boolean` | Optional | - | Boolean getNonOwnerEditable() | setNonOwnerEditable(Boolean nonOwnerEditable) |
| `NumStars` | `Integer` | Optional | - | Integer getNumStars() | setNumStars(Integer numStars) |
| `OriginalH` | `Integer` | Optional | - | Integer getOriginalH() | setOriginalH(Integer originalH) |
| `OriginalW` | `Integer` | Optional | - | Integer getOriginalW() | setOriginalW(Integer originalW) |
| `Permalink` | `String` | Optional | - | String getPermalink() | setPermalink(String permalink) |
| `PermalinkPublic` | `String` | Optional | - | String getPermalinkPublic() | setPermalinkPublic(String permalinkPublic) |
| `PinnedInfo` | `Object` | Optional | - | Object getPinnedInfo() | setPinnedInfo(Object pinnedInfo) |
| `PinnedTo` | `List<String>` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` | List<String> getPinnedTo() | setPinnedTo(List<String> pinnedTo) |
| `PrettyType` | `String` | Optional | - | String getPrettyType() | setPrettyType(String prettyType) |
| `Preview` | `String` | Optional | - | String getPreview() | setPreview(String preview) |
| `PublicUrlShared` | `Boolean` | Optional | - | Boolean getPublicUrlShared() | setPublicUrlShared(Boolean publicUrlShared) |
| `Reactions` | [`List<ReactionObject>`](../../doc/models/reaction-object.md) | Optional | - | List<ReactionObject> getReactions() | setReactions(List<ReactionObject> reactions) |
| `Shares` | [`Shares`](../../doc/models/shares.md) | Optional | - | Shares getShares() | setShares(Shares shares) |
| `Size` | `Integer` | Optional | - | Integer getSize() | setSize(Integer size) |
| `SourceTeam` | `String` | Optional | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` | String getSourceTeam() | setSourceTeam(String sourceTeam) |
| `State` | `String` | Optional | - | String getState() | setState(String state) |
| `Thumb1024` | `String` | Optional | - | String getThumb1024() | setThumb1024(String thumb1024) |
| `Thumb1024H` | `Integer` | Optional | - | Integer getThumb1024H() | setThumb1024H(Integer thumb1024H) |
| `Thumb1024W` | `Integer` | Optional | - | Integer getThumb1024W() | setThumb1024W(Integer thumb1024W) |
| `Thumb160` | `String` | Optional | - | String getThumb160() | setThumb160(String thumb160) |
| `Thumb360` | `String` | Optional | - | String getThumb360() | setThumb360(String thumb360) |
| `Thumb360H` | `Integer` | Optional | - | Integer getThumb360H() | setThumb360H(Integer thumb360H) |
| `Thumb360W` | `Integer` | Optional | - | Integer getThumb360W() | setThumb360W(Integer thumb360W) |
| `Thumb480` | `String` | Optional | - | String getThumb480() | setThumb480(String thumb480) |
| `Thumb480H` | `Integer` | Optional | - | Integer getThumb480H() | setThumb480H(Integer thumb480H) |
| `Thumb480W` | `Integer` | Optional | - | Integer getThumb480W() | setThumb480W(Integer thumb480W) |
| `Thumb64` | `String` | Optional | - | String getThumb64() | setThumb64(String thumb64) |
| `Thumb720` | `String` | Optional | - | String getThumb720() | setThumb720(String thumb720) |
| `Thumb720H` | `Integer` | Optional | - | Integer getThumb720H() | setThumb720H(Integer thumb720H) |
| `Thumb720W` | `Integer` | Optional | - | Integer getThumb720W() | setThumb720W(Integer thumb720W) |
| `Thumb80` | `String` | Optional | - | String getThumb80() | setThumb80(String thumb80) |
| `Thumb800` | `String` | Optional | - | String getThumb800() | setThumb800(String thumb800) |
| `Thumb800H` | `Integer` | Optional | - | Integer getThumb800H() | setThumb800H(Integer thumb800H) |
| `Thumb800W` | `Integer` | Optional | - | Integer getThumb800W() | setThumb800W(Integer thumb800W) |
| `Thumb960` | `String` | Optional | - | String getThumb960() | setThumb960(String thumb960) |
| `Thumb960H` | `Integer` | Optional | - | Integer getThumb960H() | setThumb960H(Integer thumb960H) |
| `Thumb960W` | `Integer` | Optional | - | Integer getThumb960W() | setThumb960W(Integer thumb960W) |
| `ThumbTiny` | `String` | Optional | - | String getThumbTiny() | setThumbTiny(String thumbTiny) |
| `Timestamp` | `Integer` | Optional | - | Integer getTimestamp() | setTimestamp(Integer timestamp) |
| `Title` | `String` | Optional | - | String getTitle() | setTitle(String title) |
| `Updated` | `Integer` | Optional | - | Integer getUpdated() | setUpdated(Integer updated) |
| `UrlPrivate` | `String` | Optional | - | String getUrlPrivate() | setUrlPrivate(String urlPrivate) |
| `UrlPrivateDownload` | `String` | Optional | - | String getUrlPrivateDownload() | setUrlPrivateDownload(String urlPrivateDownload) |
| `User` | `String` | Optional | - | String getUser() | setUser(String user) |
| `UserTeam` | `String` | Optional | **Constraints**: *Pattern*: `^[T][A-Z0-9]{2,}$` | String getUserTeam() | setUserTeam(String userTeam) |
| `Username` | `String` | Optional | - | String getUsername() | setUsername(String username) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channels": [
    "channels3",
    "channels2",
    "channels1"
  ],
  "comments_count": 94,
  "created": 2,
  "date_delete": 156,
  "display_as_bot": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

