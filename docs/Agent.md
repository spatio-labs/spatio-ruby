# Spatio::Agent

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **name** | **String** |  | [optional] |
| **description** | **String** |  | [optional] |
| **system_prompt** | **String** |  | [optional] |
| **tools** | **Array&lt;String&gt;** |  | [optional] |
| **icon** | **String** |  | [optional] |
| **color** | **String** |  | [optional] |
| **is_default** | **Boolean** |  | [optional] |
| **is_preconfigured** | **Boolean** |  | [optional] |
| **created_at** | **Time** |  | [optional] |
| **updated_at** | **Time** |  | [optional] |
| **metadata** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Agent.new(
  id: null,
  name: null,
  description: null,
  system_prompt: null,
  tools: null,
  icon: null,
  color: null,
  is_default: null,
  is_preconfigured: null,
  created_at: null,
  updated_at: null,
  metadata: null
)
```

