
# Dnd End Snooze Schema

Schema for successful response from dnd.endSnooze method

*This model accepts additional fields of type Object.*

## Structure

`DndEndSnoozeSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `DndEnabled` | `boolean` | Required | - | boolean getDndEnabled() | setDndEnabled(boolean dndEnabled) |
| `NextDndEndTs` | `int` | Required | - | int getNextDndEndTs() | setNextDndEndTs(int nextDndEndTs) |
| `NextDndStartTs` | `int` | Required | - | int getNextDndStartTs() | setNextDndStartTs(int nextDndStartTs) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `SnoozeEnabled` | `boolean` | Required | - | boolean getSnoozeEnabled() | setSnoozeEnabled(boolean snoozeEnabled) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "dnd_enabled": false,
  "next_dnd_end_ts": 248,
  "next_dnd_start_ts": 88,
  "ok": "True",
  "snooze_enabled": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

