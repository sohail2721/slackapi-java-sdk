
# Dnd Info Schema

Schema for successful response from dnd.info method

*This model accepts additional fields of type Object.*

## Structure

`DndInfoSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `DndEnabled` | `boolean` | Required | - | boolean getDndEnabled() | setDndEnabled(boolean dndEnabled) |
| `NextDndEndTs` | `int` | Required | - | int getNextDndEndTs() | setNextDndEndTs(int nextDndEndTs) |
| `NextDndStartTs` | `int` | Required | - | int getNextDndStartTs() | setNextDndStartTs(int nextDndStartTs) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `SnoozeEnabled` | `Boolean` | Optional | - | Boolean getSnoozeEnabled() | setSnoozeEnabled(Boolean snoozeEnabled) |
| `SnoozeEndtime` | `Integer` | Optional | - | Integer getSnoozeEndtime() | setSnoozeEndtime(Integer snoozeEndtime) |
| `SnoozeRemaining` | `Integer` | Optional | - | Integer getSnoozeRemaining() | setSnoozeRemaining(Integer snoozeRemaining) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "dnd_enabled": false,
  "next_dnd_end_ts": 138,
  "next_dnd_start_ts": 198,
  "ok": "True",
  "snooze_enabled": false,
  "snooze_endtime": 96,
  "snooze_remaining": 96,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

