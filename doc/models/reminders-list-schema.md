
# Reminders List Schema

Schema for successful response from reminders.list method

*This model accepts additional fields of type Object.*

## Structure

`RemindersListSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Reminders` | [`List<ObjsReminder>`](../../doc/models/objs-reminder.md) | Required | - | List<ObjsReminder> getReminders() | setReminders(List<ObjsReminder> reminders) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "reminders": [
    {
      "complete_ts": 28,
      "creator": "creator0",
      "id": "id2",
      "recurring": false,
      "text": "text2",
      "time": 186,
      "user": "user2",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

