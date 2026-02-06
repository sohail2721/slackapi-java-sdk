
# Conversations Close Success Schema

Schema for successful response conversations.close method

*This model accepts additional fields of type Object.*

## Structure

`ConversationsCloseSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AlreadyClosed` | `Boolean` | Optional | - | Boolean getAlreadyClosed() | setAlreadyClosed(Boolean alreadyClosed) |
| `NoOp` | `Boolean` | Optional | - | Boolean getNoOp() | setNoOp(Boolean noOp) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "already_closed": false,
  "no_op": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

