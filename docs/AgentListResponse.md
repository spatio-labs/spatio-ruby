# Spatio::AgentListResponse

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **agents** | [**Array&lt;Agent&gt;**](Agent.md) |  |  |
| **has_more** | **Boolean** |  | [optional] |
| **total** | **Integer** |  | [optional] |
| **total_count** | **Integer** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::AgentListResponse.new(
  agents: null,
  has_more: null,
  total: null,
  total_count: null
)
```

