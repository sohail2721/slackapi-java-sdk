
# Usergroups Users Update Error Schema Exception

Schema for error response from usergroups.users.update method

*This model accepts additional fields of type Object.*

## Structure

`UsergroupsUsersUpdateErrorSchemaException`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Callstack` | `String` | Optional | Note: PHP callstack is only visible in dev/qa | String getCallstack() | setCallstack(String callstack) |
| `Error` | [`Error86`](../../doc/models/error-86.md) | Required | - | Error86 getError() | setError(Error86 error) |
| `Ok` | `String` | Required, Constant | **Value**: `"False"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "error": "no_permission",
  "ok": "False",
  "callstack": "callstack6",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

