
# Conversations Info Error Schema Exception

Schema for error response from conversations.info method

*This model accepts additional fields of type Object.*

## Structure

`ConversationsInfoErrorSchemaException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Callstack` | `String` | Optional | Note: PHP callstack is only visible in dev/qa | String getCallstack() | setCallstack(String callstack) |
| `Error` | [`Error34`](../../doc/models/error-34.md) | Required | - | Error34 getError() | setError(Error34 error) |
| `Needed` | `String` | Optional | - | String getNeeded() | setNeeded(String needed) |
| `Ok` | `String` | Required, Constant | **Value**: `"False"` | String getOk() | setOk(String ok) |
| `Provided` | `String` | Optional | - | String getProvided() | setProvided(String provided) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "error": "team_added_to_org",
  "ok": "False",
  "callstack": "callstack8",
  "needed": "needed8",
  "provided": "provided8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

