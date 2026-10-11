# # PostVersion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **int** | Use &#x60;0&#x60; for the original/default version. |
**is_original** | **bool** | Must be &#x60;true&#x60; for the first version. |
**synced_with** | **int** | Account ID of the version this version follows (&#x60;0&#x60; &#x3D; the original), or null when it is edited independently. Ignored on the original version. | [optional]
**content** | [**\PostBoostClient\Model\PostContent[]**](PostContent.md) |  |
**options** | **object** | Platform-specific publishing options. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
