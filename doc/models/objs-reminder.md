
# Objs Reminder

*This model accepts additional fields of type Object.*

## Structure

`ObjsReminder`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `CompleteTs` | `Integer` | Optional | - | Integer getCompleteTs() | setCompleteTs(Integer completeTs) |
| `Creator` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getCreator() | setCreator(String creator) |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^Rm[A-Z0-9]{8,}$` | String getId() | setId(String id) |
| `Recurring` | `boolean` | Required | - | boolean getRecurring() | setRecurring(boolean recurring) |
| `Text` | `String` | Required | - | String getText() | setText(String text) |
| `Time` | `Integer` | Optional | - | Integer getTime() | setTime(Integer time) |
| `User` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getUser() | setUser(String user) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "complete_ts": 102,
  "creator": "creator4",
  "id": "id6",
  "recurring": false,
  "text": "text4",
  "time": 252,
  "user": "user6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

