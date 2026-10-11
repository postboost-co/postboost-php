# # SchedulePostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**post_now** | **bool** |  |
**date** | **\DateTime** | New date for the post (Y-m-d). Use together with &#x60;time&#x60;. | [optional]
**time** | **string** | New time for the post (H:i). | [optional]
**timezone** | **string** | Timezone &#x60;date&#x60;, &#x60;time&#x60; and &#x60;accounts_schedule&#x60; are read in. Defaults to the workspace timezone. | [optional]
**accounts_schedule** | [**\PostBoostClient\Model\AccountSchedule[]**](AccountSchedule.md) | Per-account departure times. When omitted, accounts keep their offsets from the post time. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
