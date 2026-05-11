# Spatio::Draft

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **message_id** | **String** |  |  |
| **thread_id** | **String** |  | [optional] |
| **to** | **Array&lt;String&gt;** |  | [optional] |
| **cc** | **Array&lt;String&gt;** |  | [optional] |
| **bcc** | **Array&lt;String&gt;** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |
| **html** | **Boolean** |  |  |
| **attachments** | [**Array&lt;AttachmentMeta&gt;**](AttachmentMeta.md) |  | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Draft.new(
  id: null,
  message_id: null,
  thread_id: null,
  to: null,
  cc: null,
  bcc: null,
  subject: null,
  body: null,
  html: null,
  attachments: null,
  created_at: null,
  updated_at: null
)
```

