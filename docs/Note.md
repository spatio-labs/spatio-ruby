# Spatio::Note

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** | Stable provider id for the note. |  |
| **provider** | **String** | Registered provider id (e.g. &#x60;native-notes&#x60;). | [optional] |
| **account_id** | **String** | Connected-account row this note belongs to. | [optional] |
| **owner_user_id** | **String** | User id of the note&#39;s owner. Surfaced so the renderer can show \&quot;Shared with you\&quot; when &#x60;ownerUserId&#x60; differs from the viewer&#39;s id. Empty for non-native providers.  | [optional] |
| **title** | **String** |  |  |
| **content** | **String** | Markdown body. The block tree at &#x60;/v1/notes/{id}/blocks&#x60; is the canonical structured representation; &#x60;content&#x60; is a flattened markdown view kept for clients that don&#39;t render blocks.  |  |
| **icon** | **String** | Emoji or short string used as the note&#39;s icon. | [optional] |
| **cover_image** | **String** | URL of the note&#39;s cover image. | [optional] |
| **parent_id** | **String** | Parent note id when notes are nested. | [optional] |
| **properties** | **Hash&lt;String, Object&gt;** | Free-form provider-specific properties (tags, etc.). | [optional] |
| **archived** | **Boolean** |  |  |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **last_edited_by** | **String** | User id of the most recent editor. | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::Note.new(
  id: null,
  provider: null,
  account_id: null,
  owner_user_id: null,
  title: null,
  content: null,
  icon: null,
  cover_image: null,
  parent_id: null,
  properties: null,
  archived: null,
  created_at: null,
  updated_at: null,
  last_edited_by: null
)
```

