
# Objs Enterprise User

*This model accepts additional fields of type Object.*

## Structure

`ObjsEnterpriseUser`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `EnterpriseId` | `String` | Required | **Constraints**: *Pattern*: `^[E][A-Z0-9]{8,}$` | String getEnterpriseId() | setEnterpriseId(String enterpriseId) |
| `EnterpriseName` | `String` | Required | - | String getEnterpriseName() | setEnterpriseName(String enterpriseName) |
| `Id` | `String` | Required | **Constraints**: *Pattern*: `^[WU][A-Z0-9]{8,}$` | String getId() | setId(String id) |
| `IsAdmin` | `boolean` | Required | - | boolean getIsAdmin() | setIsAdmin(boolean isAdmin) |
| `IsOwner` | `boolean` | Required | - | boolean getIsOwner() | setIsOwner(boolean isOwner) |
| `Teams` | `List<String>` | Required | **Constraints**: *Unique Items Required*, *Pattern*: `^[T][A-Z0-9]{2,}$` | List<String> getTeams() | setTeams(List<String> teams) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "enterprise_id": "enterprise_id0",
  "enterprise_name": "enterprise_name0",
  "id": "id0",
  "is_admin": false,
  "is_owner": false,
  "teams": [
    "teams3",
    "teams4",
    "teams5"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

