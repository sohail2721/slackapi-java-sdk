
# Team

*This model accepts additional fields of type Object.*

## Structure

`Team`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Resources` | [`ResourcesInInfoFromAppsPermissionsInfo`](../../doc/models/resources-in-info-from-apps-permissions-info.md) | Required | - | ResourcesInInfoFromAppsPermissionsInfo getResources() | setResources(ResourcesInInfoFromAppsPermissionsInfo resources) |
| `Scopes` | `List<String>` | Required | - | List<String> getScopes() | setScopes(List<String> scopes) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "resources": {
    "excluded_ids": [
      {
        "key1": "val1",
        "key2": "val2"
      },
      {
        "key1": "val1",
        "key2": "val2"
      },
      {
        "key1": "val1",
        "key2": "val2"
      }
    ],
    "ids": [
      {
        "key1": "val1",
        "key2": "val2"
      },
      {
        "key1": "val1",
        "key2": "val2"
      },
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
  },
  "scopes": [
    "scopes2"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

