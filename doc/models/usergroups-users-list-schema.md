
# Usergroups Users List Schema

Schema for successful response from usergroups.users.list method

*This model accepts additional fields of type Object.*

## Structure

`UsergroupsUsersListSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Users` | `List<String>` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | List<String> getUsers() | setUsers(List<String> users) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "users": [
    "users3"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

