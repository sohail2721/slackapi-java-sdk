
# Scheduled Message

*This model accepts additional fields of type Object.*

## Structure

`ScheduledMessage`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ChannelId` | `String` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` | String getChannelId() | setChannelId(String channelId) |
| `DateCreated` | `int` | Required | - | int getDateCreated() | setDateCreated(int dateCreated) |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^[Q][A-Z0-9]{8,}$` | String getId() | setId(String id) |
| `PostAt` | `int` | Required | - | int getPostAt() | setPostAt(int postAt) |
| `Text` | `String` | Optional | - | String getText() | setText(String text) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channel_id": "channel_id4",
  "date_created": 228,
  "id": "id8",
  "post_at": 128,
  "text": "text8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

