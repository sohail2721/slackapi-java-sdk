
# Attachment

*This model accepts additional fields of type Object.*

## Structure

`Attachment`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Fallback` | `String` | Optional | - | String getFallback() | setFallback(String fallback) |
| `Id` | `int` | Required | - | int getId() | setId(int id) |
| `ImageBytes` | `Integer` | Optional | - | Integer getImageBytes() | setImageBytes(Integer imageBytes) |
| `ImageHeight` | `Integer` | Optional | - | Integer getImageHeight() | setImageHeight(Integer imageHeight) |
| `ImageUrl` | `String` | Optional | - | String getImageUrl() | setImageUrl(String imageUrl) |
| `ImageWidth` | `Integer` | Optional | - | Integer getImageWidth() | setImageWidth(Integer imageWidth) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "fallback": "fallback4",
  "id": 158,
  "image_bytes": 168,
  "image_height": 20,
  "image_url": "image_url6",
  "image_width": 146,
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

