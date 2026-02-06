
# Log

*This model accepts additional fields of type Object.*

## Structure

`Log`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AdminAppId` | `String` | Optional | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` | String getAdminAppId() | setAdminAppId(String adminAppId) |
| `AppId` | `String` | Required | **Constraints**: *Pattern*: `^A[A-Z0-9]{1,}$` | String getAppId() | setAppId(String appId) |
| `AppType` | `String` | Required | - | String getAppType() | setAppType(String appType) |
| `ChangeType` | `String` | Required | - | String getChangeType() | setChangeType(String changeType) |
| `Channel` | `String` | Optional | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` | String getChannel() | setChannel(String channel) |
| `Date` | `String` | Required | - | String getDate() | setDate(String date) |
| `Scope` | `String` | Required | - | String getScope() | setScope(String scope) |
| `ServiceId` | `String` | Optional | - | String getServiceId() | setServiceId(String serviceId) |
| `ServiceType` | `String` | Optional | - | String getServiceType() | setServiceType(String serviceType) |
| `UserId` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getUserId() | setUserId(String userId) |
| `UserName` | `String` | Required | - | String getUserName() | setUserName(String userName) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "admin_app_id": "admin_app_id2",
  "app_id": "app_id2",
  "app_type": "app_type8",
  "change_type": "change_type2",
  "channel": "channel0",
  "date": "date0",
  "scope": "scope8",
  "service_id": "service_id6",
  "service_type": "service_type0",
  "user_id": "user_id2",
  "user_name": "user_name0",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

