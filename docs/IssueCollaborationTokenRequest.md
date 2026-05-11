# Spatio::IssueCollaborationTokenRequest

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **room** | **String** | Optional &#x60;&lt;type&gt;:&lt;id&gt;&#x60; room identifier (e.g. &#x60;note:abc123&#x60;). When set, the JWT only authorizes this single room.  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::IssueCollaborationTokenRequest.new(
  room: note:abc123
)
```

