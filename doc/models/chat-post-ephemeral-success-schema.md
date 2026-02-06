
# Chat Post Ephemeral Success Schema

Schema for successful response from chat.postEphemeral method

*This model accepts additional fields of type Object.*

## Structure

`ChatPostEphemeralSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `MessageTs` | `String` | Required | **Constraints**: *Pattern*: `^\d{10}\.\d{6}$` | String getMessageTs() | setMessageTs(String messageTs) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "message_ts": "message_ts0",
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

