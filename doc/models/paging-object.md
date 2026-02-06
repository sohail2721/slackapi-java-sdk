
# Paging Object

*This model accepts additional fields of type Object.*

## Structure

`PagingObject`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Count` | `Integer` | Optional | - | Integer getCount() | setCount(Integer count) |
| `Page` | `int` | Required | - | int getPage() | setPage(int page) |
| `Pages` | `Integer` | Optional | - | Integer getPages() | setPages(Integer pages) |
| `PerPage` | `Integer` | Optional | - | Integer getPerPage() | setPerPage(Integer perPage) |
| `Spill` | `Integer` | Optional | - | Integer getSpill() | setSpill(Integer spill) |
| `Total` | `int` | Required | - | int getTotal() | setTotal(int total) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "count": 190,
  "page": 160,
  "pages": 28,
  "per_page": 72,
  "spill": 132,
  "total": 140,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

