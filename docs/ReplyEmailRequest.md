# Spatio::ReplyEmailRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **to** | **Array&lt;String&gt;** |  | [optional] |
| **cc** | **Array&lt;String&gt;** |  | [optional] |
| **bcc** | **Array&lt;String&gt;** |  | [optional] |
| **body** | **String** |  |  |
| **html** | **Boolean** |  | [optional] |
| **attachments** | [**Array&lt;AttachmentInput&gt;**](AttachmentInput.md) |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ReplyEmailRequest.new(
  account_id: null,
  to: null,
  cc: null,
  bcc: null,
  body: null,
  html: null,
  attachments: null
)
```

