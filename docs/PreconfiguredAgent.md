# Spatio::PreconfiguredAgent

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **agent_id** | **String** |  |  |
| **name** | **String** |  |  |
| **tagline** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **icon** | **String** |  | [optional] |
| **has_all_tools** | **Boolean** |  | [optional] |
| **tool_count** | **Integer** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::PreconfiguredAgent.new(
  agent_id: null,
  name: null,
  tagline: null,
  description: null,
  icon: null,
  has_all_tools: null,
  tool_count: null
)
```

