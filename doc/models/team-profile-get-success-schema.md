
# Team Profile Get Success Schema

Schema for successful response from team.profile.get method

*This model accepts additional fields of type Object.*

## Structure

`TeamProfileGetSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Profile` | [`Profile`](../../doc/models/profile.md) | Required | - | Profile getProfile() | setProfile(Profile profile) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "profile": {
    "fields": [
      {
        "field_name": "field_name2",
        "hint": "hint8",
        "id": "id8",
        "is_hidden": false,
        "label": "label8",
        "options": {
          "key1": "val1",
          "key2": "val2"
        },
        "ordering": 158.68,
        "possible_values": [
          "possible_values9",
          "possible_values0"
        ],
        "type": "options_list",
        "exampleAdditionalProperty": {
          "key1": "val1",
          "key2": "val2"
        }
      }
    ],
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

