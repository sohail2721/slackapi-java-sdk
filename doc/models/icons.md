
# Icons

*This model accepts additional fields of type Object.*

## Structure

`Icons`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Image36` | `String` | Required | - | String getImage36() | setImage36(String image36) |
| `Image48` | `String` | Required | - | String getImage48() | setImage48(String image48) |
| `Image72` | `String` | Required | - | String getImage72() | setImage72(String image72) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "image_36": "image_360",
  "image_48": "image_480",
  "image_72": "image_726",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

