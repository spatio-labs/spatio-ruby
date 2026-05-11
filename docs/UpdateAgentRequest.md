# Spatio::UpdateAgentRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **system_prompt** | **String** |  | [optional] |
| **tools** | **Array&lt;String&gt;** |  | [optional] |
| **icon** | **String** |  | [optional] |
| **color** | **String** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::UpdateAgentRequest.new(
  name: null,
  description: null,
  system_prompt: null,
  tools: null,
  icon: null,
  color: null,
  metadata: null
)
```

