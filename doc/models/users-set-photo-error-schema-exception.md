
# Users Set Photo Error Schema Exception

Schema for error response from users.setPhoto method

*This model accepts additional fields of type Object.*

## Structure

`UsersSetPhotoErrorSchemaException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Callstack` | `String` | Optional | Note: PHP callstack is only visible in dev/qa | String getCallstack() | setCallstack(String callstack) |
| `DebugStep` | `String` | Optional | possibly DEV/QA only | String getDebugStep() | setDebugStep(String debugStep) |
| `Dims` | `String` | Optional | possibly DEV/QA only | String getDims() | setDims(String dims) |
| `Error` | [`Error98`](../../doc/models/error-98.md) | Required | - | Error98 getError() | setError(Error98 error) |
| `Ok` | `String` | Required, Constant | **Value**: `"False"` | String getOk() | setOk(String ok) |
| `TimeIdent` | `Integer` | Optional | possibly DEV/QA only | Integer getTimeIdent() | setTimeIdent(Integer timeIdent) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "error": "account_inactive",
  "ok": "False",
  "callstack": "callstack4",
  "debug_step": "debug_step0",
  "dims": "dims8",
  "time_ident": 18,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

