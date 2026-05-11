# Spatio::Channel

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **provider** | **String** | Registered provider id (e.g. &#x60;slack&#x60;, &#x60;native-chat&#x60;).  | [optional] |
| **account_id** | **String** |  | [optional] |
| **name** | **String** |  |  |
| **type** | **String** | Provider-specific. Common canonicals: &#x60;channel&#x60; and &#x60;private&#x60; (group channels), &#x60;im&#x60; (1:1 DM), &#x60;mpim&#x60; (group DM).  |  |
| **description** | **String** |  | [optional] |
| **topic** | **String** |  | [optional] |
| **is_member** | **Boolean** |  |  |
| **is_archived** | **Boolean** |  |  |
| **member_count** | **Integer** |  | [optional] |
| **created_at** | **Time** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Channel.new(
  id: null,
  provider: null,
  account_id: null,
  name: null,
  type: null,
  description: null,
  topic: null,
  is_member: null,
  is_archived: null,
  member_count: null,
  created_at: null
)
```

