# # BlogToSocialResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**blog_title** | **string** | The blog post title (scraped or provided directly). | [optional]
**blog_excerpt** | **string** | A short excerpt from the blog post content. | [optional]
**captions** | [**\PostBoostClient\Model\BlogToSocialCaption[]**](BlogToSocialCaption.md) | Generated captions, one per target account. | [optional]
**post_uuid** | **string** | UUID of the created draft post. Only present when &#x60;create_post&#x60; was &#x60;true&#x60;. | [optional]
**media** | [**\PostBoostClient\Model\BlogToSocialMedia**](BlogToSocialMedia.md) |  | [optional]
**credits_used** | **int** | Number of AI credits consumed by this request (one per successful caption). | [optional]
**credits_remaining** | **int** | Remaining AI credits for the current billing period. &#x60;null&#x60; for unlimited plans. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
