
# External Org Migrations

*This model accepts additional fields of type Object.*

## Structure

`ExternalOrgMigrations`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Current` | [`List<Current>`](../../doc/models/current.md) | Required | - | List<Current> getCurrent() | setCurrent(List<Current> current) |
| `DateUpdated` | `int` | Required | - | int getDateUpdated() | setDateUpdated(int dateUpdated) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "current": [
    {
      "date_started": 84,
      "team_id": "team_id0",
      "exampleAdditionalProperty": {
        "key1": "val1",
        "key2": "val2"
      }
    }
  ],
  "date_updated": 8,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

