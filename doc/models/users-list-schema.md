
# Users List Schema

Schema for successful response from users.list method

*This model accepts additional fields of type Object.*

## Structure

`UsersListSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `CacheTs` | `int` | Required | - | int getCacheTs() | setCacheTs(int cacheTs) |
| `Members` | `List<Object>` | Required | **Constraints**: *Minimum Items*: `1`, *Unique Items Required* | List<Object> getMembers() | setMembers(List<Object> members) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `ResponseMetadata` | `Object` | Optional | - | Object getResponseMetadata() | setResponseMetadata(Object responseMetadata) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "cache_ts": 154,
  "members": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "ok": "True",
  "response_metadata": {
    "key1": "val1",
    "key2": "val2"
  },
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

