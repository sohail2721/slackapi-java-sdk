
# Prefs

*This model accepts additional fields of type Object.*

## Structure

`Prefs`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Channels` | `List<String>` | Required | **Constraints**: *Pattern*: `^[C][A-Z0-9]{2,}$` | List<String> getChannels() | setChannels(List<String> channels) |
| `Groups` | `List<String>` | Required | **Constraints**: *Pattern*: `^[G][A-Z0-9]{8,}$` | List<String> getGroups() | setGroups(List<String> groups) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "channels": [
    "channels3",
    "channels4",
    "channels5"
  ],
  "groups": [
    "groups6",
    "groups7"
  ],
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

