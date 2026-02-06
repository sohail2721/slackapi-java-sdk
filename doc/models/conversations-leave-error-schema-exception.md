
# Conversations Leave Error Schema Exception

Schema for error response from conversations.leave method

*This model accepts additional fields of type Object.*

## Structure

`ConversationsLeaveErrorSchemaException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Callstack` | `String` | Optional | Note: PHP callstack is only visible in dev/qa | String getCallstack() | setCallstack(String callstack) |
| `Error` | [`Error39`](../../doc/models/error-39.md) | Required | - | Error39 getError() | setError(Error39 error) |
| `Needed` | `String` | Optional | - | String getNeeded() | setNeeded(String needed) |
| `Ok` | `String` | Required, Constant | **Value**: `"False"` | String getOk() | setOk(String ok) |
| `Provided` | `String` | Optional | - | String getProvided() | setProvided(String provided) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "error": "missing_charset",
  "ok": "False",
  "callstack": "callstack6",
  "needed": "needed0",
  "provided": "provided6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

