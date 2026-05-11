# Spatio::AgentSessionContext

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **user** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **current_organization** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **current_workspace** | **Hash&lt;String, Object&gt;** |  | [optional] |
| **connected_accounts** | **Array&lt;Hash&lt;String, Object&gt;&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::AgentSessionContext.new(
  user: null,
  current_organization: null,
  current_workspace: null,
  connected_accounts: null
)
```

