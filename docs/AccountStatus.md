# Spatio::AccountStatus

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **provider** | **String** | Provider id (e.g. &#x60;native-notes&#x60;, &#x60;notion&#x60;, &#x60;google-keep&#x60;). |  |
| **account_id** | **String** | Connected-account row id. |  |
| **account_name** | **String** | Human-readable label for the account, when available. | [optional] |
| **status** | **String** | - &#x60;ok&#x60; — provider call returned without error. - &#x60;error&#x60; — provider call failed; details in &#x60;error&#x60;. - &#x60;skipped&#x60; — connection was filtered out before the provider   call ran. Reserved; not currently emitted by the runtime.  |  |
| **error** | [**AccountError**](AccountError.md) |  | [optional] |
| **next_page_token** | **String** | Provider-specific cursor for the next page, if any. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::AccountStatus.new(
  provider: null,
  account_id: null,
  account_name: null,
  status: null,
  error: null,
  next_page_token: null
)
```

