# Spatio::CreateAgentRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **name** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **system_prompt** | **String** |  | [optional] |
| **tools** | **Array&lt;String&gt;** |  | [optional] |
| **icon** | **String** |  | [optional] |
| **color** | **String** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::CreateAgentRequest.new(
  name: null,
  description: null,
  system_prompt: null,
  tools: null,
  icon: null,
  color: null,
  metadata: null
)
```

