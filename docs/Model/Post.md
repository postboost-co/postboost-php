# # Post

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
**scheduled_at** | **\DateTime** |  | [optional]
**published_at** | **\DateTime** |  | [optional]
**created_at** | **\DateTime** |  |
**trashed** | **bool** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
