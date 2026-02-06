
# Profile 1

*This model accepts additional fields of type Object.*

## Structure

`Profile1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AvatarHash` | `String` | Required | **Constraints**: *Pattern*: `^[0-9a-f]{12}$` | String getAvatarHash() | setAvatarHash(String avatarHash) |
| `Image1024` | `String` | Required | - | String getImage1024() | setImage1024(String image1024) |
| `Image192` | `String` | Required | - | String getImage192() | setImage192(String image192) |
| `Image24` | `String` | Required | - | String getImage24() | setImage24(String image24) |
| `Image32` | `String` | Required | - | String getImage32() | setImage32(String image32) |
| `Image48` | `String` | Required | - | String getImage48() | setImage48(String image48) |
| `Image512` | `String` | Required | - | String getImage512() | setImage512(String image512) |
| `Image72` | `String` | Required | - | String getImage72() | setImage72(String image72) |
| `ImageOriginal` | `String` | Required | - | String getImageOriginal() | setImageOriginal(String imageOriginal) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "avatar_hash": "avatar_hash6",
  "image_1024": "image_10242",
  "image_192": "image_1922",
  "image_24": "image_242",
  "image_32": "image_322",
  "image_48": "image_484",
  "image_512": "image_5128",
  "image_72": "image_720",
  "image_original": "image_original2",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

