
# Current

*This model accepts additional fields of type Object.*

## Structure

`Current`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `DateStarted` | `int` | Required | - | int getDateStarted() | setDateStarted(int dateStarted) |
| `TeamId` | `String` | Required | - | String getTeamId() | setTeamId(String teamId) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "date_started": 30,
  "team_id": "team_id4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

