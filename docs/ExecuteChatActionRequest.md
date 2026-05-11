# Spatio::ExecuteChatActionRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **action_id** | **String** |  |  |
| **params** | **Object** | Action-specific parameters. Free-form because the shape depends on &#x60;action_id&#x60;. See &#x60;GET /actions&#x60; for the per-id contract.  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::ExecuteChatActionRequest.new(
  action_id: null,
  params: null
)
```

