# Spatio::TaskProvidersInfo

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **providers** | **Array&lt;String&gt;** | Registered provider ids (e.g. &#x60;native-tasks&#x60;, &#x60;linear&#x60;). |  |
| **platform** | [**TaskProvidersInfoPlatform**](TaskProvidersInfoPlatform.md) |  |  |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::TaskProvidersInfo.new(
  providers: null,
  platform: null
)
```

