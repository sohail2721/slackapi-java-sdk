
# Users Info Error Schema Exception

Schema for error response from users.info method

*This model accepts additional fields of type Object.*

## Structure

`UsersInfoErrorSchemaException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Callstack` | `String` | Optional | - | String getCallstack() | setCallstack(String callstack) |
| `Error` | [`Error92`](../../doc/models/error-92.md) | Required | - | Error92 getError() | setError(Error92 error) |
| `Ok` | `String` | Required, Constant | **Value**: `"False"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "error": "not_authed",
  "ok": "False",
  "callstack": "callstack4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

