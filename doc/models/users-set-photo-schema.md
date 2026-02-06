
# Users Set Photo Schema

Schema for successful response from users.setPhoto method

*This model accepts additional fields of type Object.*

## Structure

`UsersSetPhotoSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Profile` | [`Profile1`](../../doc/models/profile-1.md) | Required | - | Profile1 getProfile() | setProfile(Profile1 profile) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "profile": {
    "avatar_hash": "avatar_hash0",
    "image_1024": "image_10246",
    "image_192": "image_1926",
    "image_24": "image_248",
    "image_32": "image_326",
    "image_48": "image_488",
    "image_512": "image_5124",
    "image_72": "image_724",
    "image_original": "image_original6",
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

