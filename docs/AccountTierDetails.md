# Spatio::AccountTierDetails

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **tier** | **String** |  |  |
| **daily_api_calls** | **Integer** |  | [optional] |
| **max_connected_accounts** | **Integer** |  | [optional] |
| **max_email_sends_per_day** | **Integer** |  | [optional] |
| **max_notes** | **Integer** |  | [optional] |
| **max_sheets** | **Integer** |  | [optional] |
| **max_slides** | **Integer** |  | [optional] |
| **max_files** | **Integer** |  | [optional] |
| **max_tasks** | **Integer** |  | [optional] |
| **max_team_members** | **Integer** |  | [optional] |
| **max_workspaces** | **Integer** |  | [optional] |
| **storage_gb** | **Integer** |  | [optional] |
| **has_automations** | **Boolean** |  | [optional] |
| **has_advanced_automations** | **Boolean** |  | [optional] |
| **has_full_api_access** | **Boolean** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::AccountTierDetails.new(
  tier: null,
  daily_api_calls: null,
  max_connected_accounts: null,
  max_email_sends_per_day: null,
  max_notes: null,
  max_sheets: null,
  max_slides: null,
  max_files: null,
  max_tasks: null,
  max_team_members: null,
  max_workspaces: null,
  storage_gb: null,
  has_automations: null,
  has_advanced_automations: null,
  has_full_api_access: null
)
```

