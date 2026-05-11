# Spatio::Email

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **thread_id** | **String** |  | [optional] |
| **provider** | **String** |  | [optional] |
| **account_id** | **String** |  | [optional] |
| **subject** | **String** |  |  |
| **from** | **String** |  |  |
| **to** | **Array&lt;String&gt;** |  |  |
| **cc** | **Array&lt;String&gt;** |  | [optional] |
| **bcc** | **Array&lt;String&gt;** |  | [optional] |
| **body** | **String** |  |  |
| **html** | **Boolean** | &#x60;true&#x60; when &#x60;body&#x60; contains HTML, &#x60;false&#x60; for plain text.  |  |
| **date** | **Time** |  |  |
| **labels** | **Array&lt;String&gt;** |  | [optional] |
| **is_read** | **Boolean** |  |  |
| **is_starred** | **Boolean** |  |  |
| **attachments** | [**Array&lt;AttachmentMeta&gt;**](AttachmentMeta.md) |  | [optional] |
| **snippet** | **String** |  | [optional] |
| **message_id** | **String** | RFC 5322 Message-ID header. | [optional] |
| **in_reply_to** | **String** | RFC 5322 In-Reply-To header — the parent message id this message is a reply to.  | [optional] |
| **references** | **Array&lt;String&gt;** | RFC 5322 References header (ancestor chain). | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Email.new(
  id: null,
  thread_id: null,
  provider: null,
  account_id: null,
  subject: null,
  from: null,
  to: null,
  cc: null,
  bcc: null,
  body: null,
  html: null,
  date: null,
  labels: null,
  is_read: null,
  is_starred: null,
  attachments: null,
  snippet: null,
  message_id: null,
  in_reply_to: null,
  references: null
)
```

