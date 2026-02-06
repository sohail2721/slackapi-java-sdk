
# Resources in Info From Apps Permissions Info

*This model accepts additional fields of type Object.*

## Structure

`ResourcesInInfoFromAppsPermissionsInfo`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `ExcludedIds` | `List<Object>` | Optional | - | List<Object> getExcludedIds() | setExcludedIds(List<Object> excludedIds) |
| `Ids` | `List<Object>` | Required | - | List<Object> getIds() | setIds(List<Object> ids) |
| `Wildcard` | `Boolean` | Optional | - | Boolean getWildcard() | setWildcard(Boolean wildcard) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "excluded_ids": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ids": [
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "wildcard": false,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

