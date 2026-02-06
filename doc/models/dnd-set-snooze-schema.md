
# Dnd Set Snooze Schema

Schema for successful response from dnd.setSnooze method

*This model accepts additional fields of type Object.*

## Structure

`DndSetSnoozeSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `SnoozeEnabled` | `boolean` | Required | - | boolean getSnoozeEnabled() | setSnoozeEnabled(boolean snoozeEnabled) |
| `SnoozeEndtime` | `int` | Required | - | int getSnoozeEndtime() | setSnoozeEndtime(int snoozeEndtime) |
| `SnoozeRemaining` | `int` | Required | - | int getSnoozeRemaining() | setSnoozeRemaining(int snoozeRemaining) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "snooze_enabled": false,
  "snooze_endtime": 8,
  "snooze_remaining": 8,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

