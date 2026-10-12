# # RepurposeResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source** | [**\PostBoostClient\Model\RepurposeResultSource**](RepurposeResultSource.md) |  |
**captions** | [**\PostBoostClient\Model\BlogToSocialCaption[]**](BlogToSocialCaption.md) |  |
**slides** | [**\PostBoostClient\Model\RepurposeSlide[]**](RepurposeSlide.md) | Carousel slides in order (hook first, call to action last). Empty without a carousel. |
**media** | [**\PostBoostClient\Model\RepurposeResultMedia**](RepurposeResultMedia.md) |  | [optional]
**post_uuid** | **string** | The draft post; null when &#x60;create_post&#x60; was false. |
**credits_used** | **int** |  |
**credits_remaining** | **int** | Null for unlimited plans. |
**warnings** | **string[]** | Parts that were skipped (for example a network that gets no carousel). |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
