
# Team Integration Logs Schema

Schema for successful response from team.integrationLogs method

*This model accepts additional fields of type Object.*

## Structure

`TeamIntegrationLogsSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Logs` | [`List<Log>`](../../doc/models/log.md) | Required | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* | List<Log> getLogs() | setLogs(List<Log> logs) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Paging` | [`PagingObject`](../../doc/models/paging-object.md) | Required | - | PagingObject getPaging() | setPaging(PagingObject paging) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "logs": [
    {
      "admin_app_id": "admin_app_id6",
      "app_id": "app_id8",
      "app_type": "app_type2",
      "change_type": "change_type8",
      "channel": "channel6",
      "date": "date4",
      "scope": "scope6",
      "service_id": "service_id8",
      "service_type": "service_type4",
      "user_id": "user_id6",
      "user_name": "user_name4",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "ok": "True",
  "paging": {
    "count": 56,
    "page": 26,
    "pages": 150,
    "per_page": 194,
    "spill": 246,
    "total": 6,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

