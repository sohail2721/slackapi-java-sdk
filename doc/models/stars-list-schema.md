
# Stars List Schema

Schema for successful response from stars.list method

*This model accepts additional fields of type Object.*

## Structure

`StarsListSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Items` | `List<Object>` | Required | - | List<Object> getItems() | setItems(List<Object> items) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Paging` | [`PagingObject`](../../doc/models/paging-object.md) | Optional | - | PagingObject getPaging() | setPaging(PagingObject paging) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "items": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
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

