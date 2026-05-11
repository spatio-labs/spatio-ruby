# Spatio::AccountUsage

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **date** | **String** | Always &#x60;today&#x60; for the current-day rollup. |  |
| **api_calls** | **Integer** |  | [optional] |
| **email_sends** | **Integer** |  | [optional] |
| **notes_count** | **Integer** |  | [optional] |
| **sheets_count** | **Integer** |  | [optional] |
| **slides_count** | **Integer** |  | [optional] |
| **files_count** | **Integer** |  | [optional] |
| **tasks_count** | **Integer** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::AccountUsage.new(
  date: null,
  api_calls: null,
  email_sends: null,
  notes_count: null,
  sheets_count: null,
  slides_count: null,
  files_count: null,
  tasks_count: null
)
```

