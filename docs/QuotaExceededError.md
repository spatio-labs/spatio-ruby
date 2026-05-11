# Spatio::QuotaExceededError

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **error** | **String** | Human-readable error message. |  |
| **code** | **String** | Machine-readable error code. Stable across releases for the canonical codes (&#x60;ambiguous_account&#x60;, &#x60;no_notes_provider&#x60;, &#x60;note_not_found&#x60;). Absent for generic errors.  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::QuotaExceededError.new(
  error: user not authenticated,
  code: ambiguous_account
)
```

