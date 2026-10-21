# # PostVersion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **int** | Use &#x60;0&#x60; for the original/default version. |
**is_original** | **bool** | Must be &#x60;true&#x60; for the first version. |
**synced_with** | **int** | Account ID of the version this version follows (&#x60;0&#x60; &#x3D; the original), or null when it is edited independently. Ignored on the original version. | [optional]
**content** | [**\PostBoostClient\Model\PostContent[]**](PostContent.md) | Ordered content items. Item 0 is the post. Item 1 is the first comment on Facebook Page, Instagram and LinkedIn (LinkedIn only when first comments are enabled on this server), or the next thread post on X, Threads, Bluesky, Mastodon and Pixelfed. See &#x60;PostContent&#x60;. |
**options** | [**\PostBoostClient\Model\PostVersionOptions**](PostVersionOptions.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
