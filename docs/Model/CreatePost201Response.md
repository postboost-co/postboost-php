# # CreatePost201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**uuid** | **string** |  |
**status** | [**\PostBoostClient\Model\PostStatus**](PostStatus.md) |  |
**publish_progress** | [**\PostBoostClient\Model\PublishProgress**](PublishProgress.md) | Only present while the post is publishing. | [optional]
**accounts** | [**\PostBoostClient\Model\Account[]**](Account.md) |  |
**versions** | [**\PostBoostClient\Model\PostVersion[]**](PostVersion.md) |  |
**tags** | [**\PostBoostClient\Model\Tag[]**](Tag.md) |  |
**scheduled_at** | **string** | &#x60;Y-m-d H:i:s&#x60; in UTC (not RFC 3339). | [optional]
**published_at** | **string** | &#x60;Y-m-d H:i:s&#x60; in UTC (not RFC 3339). | [optional]
**created_at** | **string** | &#x60;Y-m-d H:i:s&#x60; in UTC (not RFC 3339). |
**trashed** | **bool** |  |
**warnings** | [**\PostBoostClient\Model\PostWarning[]**](PostWarning.md) | Present only when there is at least one warning. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
