
# Message Object 1

*This model accepts additional fields of type Object.*

## Structure

`MessageObject1`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `Attachments` | `List<Object>` | Optional | - | List<Object> getAttachments() | setAttachments(List<Object> attachments) |
| `Blocks` | `Object` | Optional | - | Object getBlocks() | setBlocks(Object blocks) |
| `Text` | `String` | Required | - | String getText() | setText(String text) |
| `AdditionalProperties` | `Map<String, Object>` | Optional | - | Object getAdditionalProperty(String key) | additionalProperty(String key, Object value) |

## Example (as JSON)

```json
{
  "attachments": [
    {
      "key1": "val1",
      "key2": "val2"
    },
    {
      "key1": "val1",
      "key2": "val2"
    }
  ],
  "blocks": {
    "key1": "val1",
    "key2": "val2"
  },
  "text": "text4",
  "exampleAdditionalProperty": {
    "key1": "val1",
    "key2": "val2"
  }
}
```

