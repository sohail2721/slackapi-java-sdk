
# Auth Revoke Schema

Schema for successful response from auth.revoke method

*This model accepts additional fields of type Object.*

## Structure

`AuthRevokeSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Revoked` | `boolean` | Required | - | boolean getRevoked() | setRevoked(boolean revoked) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "revoked": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

