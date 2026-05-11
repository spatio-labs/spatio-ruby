# Spatio::SpatioEvent

## Properties

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **id** | **String** |  |  |
| **title** | **String** |  |  |
| **description** | **String** |  | [optional] |
| **start_time** | **Time** |  |  |
| **end_time** | **Time** |  |  |
| **all_day** | **Boolean** |  |  |
| **location** | **String** |  | [optional] |
| **location_details** | **Hash&lt;String, String&gt;** | Free-form key/value (lat, lng, room, etc.). | [optional] |
| **organizer** | **String** | Organizer email. | [optional] |
| **attendees** | [**Array&lt;Attendee&gt;**](Attendee.md) |  | [optional] |
| **recurrence_rule** | **String** | RFC 5545 RRULE. | [optional] |
| **recurrence_id** | **String** | Set on instances of a recurring series. | [optional] |
| **original_start** | **Time** | Original start of a moved recurring instance. | [optional] |
| **status** | **String** | Provider-mapped event status. Free-form string — common values are &#x60;confirmed&#x60;, &#x60;tentative&#x60;, &#x60;cancelled&#x60;, &#x60;needs_action&#x60;, and the empty string when the provider doesn&#39;t populate it. Not enumerated strictly because providers add custom values and the platform passes them through verbatim.  |  |
| **visibility** | **String** | Free-form visibility string. Common values: &#x60;public&#x60;, &#x60;private&#x60;, &#x60;confidential&#x60;, plus empty when unset.  |  |
| **busy** | **Boolean** | Whether this event marks the time as busy or free. |  |
| **reminders** | [**Array&lt;Reminder&gt;**](Reminder.md) |  | [optional] |
| **travel_time_minutes** | **Integer** | Apple Calendar&#39;s local-only travel buffer. Stored on the cached row but not synced to providers that don&#39;t model it.  | [optional] |
| **categories** | **Array&lt;String&gt;** |  | [optional] |
| **color** | **String** |  | [optional] |
| **user_id** | **String** |  | [optional] |
| **account_id** | **String** |  |  |
| **provider** | **String** | Standardized provider id (e.g. &#x60;google-calendar&#x60;, &#x60;native-calendar&#x60;). Mirrors &#x60;provider_id&#x60; — both are populated on writes; clients should prefer &#x60;provider&#x60;.  | [optional] |
| **provider_id** | **String** | Legacy alias of &#x60;provider&#x60;. |  |
| **provider_data** | **Hash&lt;String, Object&gt;** | Provider-specific extras. | [optional] |
| **created_at** | **Time** |  |  |
| **updated_at** | **Time** |  |  |
| **deleted_at** | **Time** |  | [optional] |
| **synced_at** | **Time** |  | [optional] |
| **conference_data** | [**ConferenceData**](ConferenceData.md) |  | [optional] |
| **attachments** | [**Array&lt;Attachment&gt;**](Attachment.md) |  | [optional] |
| **url** | **String** |  | [optional] |
| **etag** | **String** |  | [optional] |
| **sequence** | **Integer** |  | [optional] |
| **custom_data** | **Hash&lt;String, String&gt;** |  | [optional] |

## Example

```ruby
require 'spatio-sdk'

instance = Spatio::SpatioEvent.new(
  id: null,
  title: null,
  description: null,
  start_time: null,
  end_time: null,
  all_day: null,
  location: null,
  location_details: null,
  organizer: null,
  attendees: null,
  recurrence_rule: null,
  recurrence_id: null,
  original_start: null,
  status: null,
  visibility: null,
  busy: null,
  reminders: null,
  travel_time_minutes: null,
  categories: null,
  color: null,
  user_id: null,
  account_id: null,
  provider: null,
  provider_id: null,
  provider_data: null,
  created_at: null,
  updated_at: null,
  deleted_at: null,
  synced_at: null,
  conference_data: null,
  attachments: null,
  url: null,
  etag: null,
  sequence: null,
  custom_data: null
)
```

