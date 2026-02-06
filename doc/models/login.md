
# Login

*This model accepts additional fields of type Object.*

## Structure

`Login`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Count` | `int` | Required | - | int getCount() | setCount(int count) |
| `Country` | `String` | Required | - | String getCountry() | setCountry(String country) |
| `DateFirst` | `int` | Required | - | int getDateFirst() | setDateFirst(int dateFirst) |
| `DateLast` | `int` | Required | - | int getDateLast() | setDateLast(int dateLast) |
| `Ip` | `String` | Required | - | String getIp() | setIp(String ip) |
| `Isp` | `String` | Required | - | String getIsp() | setIsp(String isp) |
| `Region` | `String` | Required | - | String getRegion() | setRegion(String region) |
| `UserAgent` | `String` | Required | - | String getUserAgent() | setUserAgent(String userAgent) |
| `UserId` | `String` | Required | **Constraints**: *Pattern*: `^[UW][A-Z0-9]{2,}$` | String getUserId() | setUserId(String userId) |
| `Username` | `String` | Required | - | String getUsername() | setUsername(String username) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "count": 110,
  "country": "country6",
  "date_first": 14,
  "date_last": 2,
  "ip": "ip6",
  "isp": "isp2",
  "region": "region8",
  "user_agent": "user_agent4",
  "user_id": "user_id0",
  "username": "username8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

