
# Scopes

*This model accepts additional fields of type Object.*

## Structure

`Scopes`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `AppHome` | `List<String>` | Optional | - | List<String> getAppHome() | setAppHome(List<String> appHome) |
| `Channel` | `List<String>` | Optional | - | List<String> getChannel() | setChannel(List<String> channel) |
| `Group` | `List<String>` | Optional | - | List<String> getGroup() | setGroup(List<String> group) |
| `Im` | `List<String>` | Optional | - | List<String> getIm() | setIm(List<String> im) |
| `Mpim` | `List<String>` | Optional | - | List<String> getMpim() | setMpim(List<String> mpim) |
| `Team` | `List<String>` | Optional | - | List<String> getTeam() | setTeam(List<String> team) |
| `User` | `List<String>` | Optional | - | List<String> getUser() | setUser(List<String> user) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "app_home": [
    "app_home2",
    "app_home1",
    "app_home0"
  ],
  "channel": [
    "channel0",
    "channel9"
  ],
  "group": [
    "group9"
  ],
  "im": [
    "im1",
    "im0",
    "im9"
  ],
  "mpim": [
    "mpim0"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

