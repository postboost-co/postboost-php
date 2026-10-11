# # PostInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**versions** | [**\PostBoostClient\Model\PostVersion[]**](PostVersion.md) | At least one version with &#x60;is_original: true&#x60; is required. |
**accounts** | **int[]** | Account IDs to publish to. | [optional]
**tags** | **int[]** | Tag IDs to attach. | [optional]
**date** | **\DateTime** |  | [optional]
**time** | **string** |  | [optional]
**timezone** | **string** | Timezone &#x60;date&#x60;, &#x60;time&#x60; and &#x60;accounts_schedule&#x60; are read in. Defaults to the workspace timezone. | [optional]
**accounts_schedule** | [**\PostBoostClient\Model\AccountSchedule[]**](AccountSchedule.md) | Per-account departure times. When omitted on update, accounts keep their offsets from the post time. | [optional]
**schedule** | **bool** | Schedule the post for the given date/time. | [optional]
**schedule_now** | **bool** | Publish immediately. | [optional]
**queue** | **bool** | Add to the smart publishing queue. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
