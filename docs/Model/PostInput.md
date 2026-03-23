# # PostInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**versions** | [**\PostBoostClient\Model\PostVersion[]**](PostVersion.md) | At least one version with &#x60;is_original: true&#x60; is required. |
**accounts** | **int[]** | Account IDs to publish to. | [optional]
**tags** | **int[]** | Tag IDs to attach. | [optional]
**date** | **\DateTime** |  | [optional]
**time** | **string** |  | [optional]
**timezone** | **string** |  | [optional]
**schedule** | **bool** | Schedule the post for the given date/time. | [optional]
**schedule_now** | **bool** | Publish immediately. | [optional]
**queue** | **bool** | Add to the smart publishing queue. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
