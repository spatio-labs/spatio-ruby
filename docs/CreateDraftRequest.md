# Spatio::CreateDraftRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **account_id** | **String** |  | [optional] |
| **to** | **Array&lt;String&gt;** |  | [optional] |
| **cc** | **Array&lt;String&gt;** |  | [optional] |
| **bcc** | **Array&lt;String&gt;** |  | [optional] |
| **subject** | **String** |  | [optional] |
| **body** | **String** |  | [optional] |
| **html** | **Boolean** |  | [optional] |
| **attachments** | [**Array&lt;AttachmentInput&gt;**](AttachmentInput.md) |  | [optional] |
| **thread_id** | **String** | Provider thread id — set when this draft is a reply, so the sent message lands inside the parent thread.  | [optional] |
| **in_reply_to** | **String** |  | [optional] |
| **references** | **Array&lt;String&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateDraftRequest.new(
  account_id: null,
  to: null,
  cc: null,
  bcc: null,
  subject: null,
  body: null,
  html: null,
  attachments: null,
  thread_id: null,
  in_reply_to: null,
  references: null
)
```

