
# Rtm Connect Schema

Schema for successful response from rtm.connect method

*This model accepts additional fields of type Object.*

## Structure

`RtmConnectSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `Self` | [`Self`](../../doc/models/self.md) | Required | - | Self getSelf() | setSelf(Self self) |
| `Team` | [`Team1`](../../doc/models/team-1.md) | Required | - | Team1 getTeam() | setTeam(Team1 team) |
| `Url` | `String` | Required | - | String getUrl() | setUrl(String url) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "ok": "True",
  "self": {
    "id": "id8",
    "name": "name8",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "team": {
    "domain": "domain6",
    "id": "id0",
    "name": "name0",
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "url": "url8",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

