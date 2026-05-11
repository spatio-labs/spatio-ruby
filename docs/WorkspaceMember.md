# Spatio::WorkspaceMember

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **role** | **String** |  |  |
| **email** | **String** |  | [optional] |
| **name** | **String** |  | [optional] |
| **avatar** | **String** |  | [optional] |
| **joined_at** | **Time** |  |  |
| **user** | **Hash&lt;String, Object&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::WorkspaceMember.new(
  id: null,
  role: null,
  email: null,
  name: null,
  avatar: null,
  joined_at: null,
  user: null
)
```

