
# Files Upload Schema

Schema for successful response files.upload method

*This model accepts additional fields of type Object.*

## Structure

`FilesUploadSchema`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `File` | [`FileObject`](../../doc/models/file-object.md) | Required | - | FileObject getFile() | setFile(FileObject file) |
| `Ok` | `String` | Required, Constant | **Value**: `"True"` | String getOk() | setOk(String ok) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "file": {
    "channels": [
      "channels5",
      "channels4"
    ],
    "comments_count": 56,
    "created": 220,
    "date_delete": 118,
    "display_as_bot": false,
    "exampleAdditionalProperty": {
      "key1": "val1",
      "key2": "val2"
    }
  },
  "ok": "True",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

