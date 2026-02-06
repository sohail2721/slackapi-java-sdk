
# Conversations Invite Error Schema 1 Exception

Schema for error response from conversations.invite method

*This model accepts additional fields of type Object.*

## Structure

`ConversationsInviteErrorSchema1Exception`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Callstack` | `String` | Optional | Note: PHP callstack is only visible in dev/qa | String getCallstack() | setCallstack(String callstack) |
| `Error` | [`Error35`](../../doc/models/error-35.md) | Optional | - | Error35 getError() | setError(Error35 error) |
| `Errors` | [`List<ErrorsIsReturnedWhenAnErrorAssociatesAnUser>`](../../doc/models/errors-is-returned-when-an-error-associates-an-user.md) | Optional | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* | List<ErrorsIsReturnedWhenAnErrorAssociatesAnUser> getErrors() | setErrors(List<ErrorsIsReturnedWhenAnErrorAssociatesAnUser> errors) |
| `Needed` | `String` | Optional | - | String getNeeded() | setNeeded(String needed) |
| `Ok` | `String` | Required, Constant | **Value**: `"False"` | String getOk() | setOk(String ok) |
| `Provided` | `String` | Optional | - | String getProvided() | setProvided(String provided) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "False",
  "callstack": "callstack2",
  "error": "invalid_post_type",
  "errors": [
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    },
    {
      "error": "user_not_found",
      "ok": "ok6",
      "user": "user0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "needed": "needed6",
  "provided": "provided2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

