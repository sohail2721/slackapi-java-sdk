
# Reminders Info Schema

Schema for successful response from reminders.info method

*This model accepts additional fields of type Object.*

## Structure

`RemindersInfoSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Reminder` | [`ObjsReminder`](../../doc/models/objs-reminder.md) | Required | - | ObjsReminder getReminder() | setReminder(ObjsReminder reminder) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "reminder": {
    "complete_ts": 136,
    "creator": "creator8",
    "id": "id0",
    "recurring": false,
    "text": "text0",
    "time": 38,
    "user": "user0",
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

