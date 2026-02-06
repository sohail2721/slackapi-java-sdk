
# Chat Delete Success Schema

Schema for successful response of chat.delete method

*This model accepts additional fields of type Object.*

## Structure

`ChatDeleteSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Channel` | `String` | Required | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` | String getChannel() | setChannel(String channel) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Ts` | `String` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` | String getTs() | setTs(String ts) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channel": "channel4",
  "ok": "True",
  "ts": "ts2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

