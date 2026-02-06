
# Chat Get Permalink Success Schema

Schema for successful response chat.getPermalink

*This model accepts additional fields of type Object.*

## Structure

`ChatGetPermalinkSuccessSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Channel` | `String` | Required | **Constraints**: *Pattern*: `^[CGD][A-Z0-9]{8,}$` | String getChannel() | setChannel(String channel) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Permalink` | `String` | Required | - | String getPermalink() | setPermalink(String permalink) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channel": "channel8",
  "ok": "True",
  "permalink": "permalink4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

