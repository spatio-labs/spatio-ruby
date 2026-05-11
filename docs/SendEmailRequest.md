# Spatio::SendEmailRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **to** | **Array&lt;String&gt;** |  |  |
| **cc** | **Array&lt;String&gt;** |  | [optional] |
| **bcc** | **Array&lt;String&gt;** |  | [optional] |
| **subject** | **String** |  |  |
| **body** | **String** |  |  |
| **html** | **Boolean** |  | [optional] |
| **attachments** | [**Array&lt;AttachmentInput&gt;**](AttachmentInput.md) |  | [optional] |
| **in_reply_to** | **String** |  | [optional] |
| **references** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SendEmailRequest.new(
  account_id: null,
  to: null,
  cc: null,
  bcc: null,
  subject: null,
  body: null,
  html: null,
  attachments: null,
  in_reply_to: null,
  references: null
)
```

