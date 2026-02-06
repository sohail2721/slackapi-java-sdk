
# Chat Me Message Schema

Schema for successful response from chat.meMessage method

*This model accepts additional fields of type Object.*

## Structure

`ChatMeMessageSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Channel` | `String` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` | String getChannel() | setChannel(String channel) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Ts` | `String` | Optional | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` | String getTs() | setTs(String ts) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "channel": "channel0",
  "ts": "ts6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

