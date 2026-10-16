# # ImageVariationsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**images** | [**\PostBoostClient\Model\Media[]**](Media.md) |  |
**aspect_ratio** | **string** |  |
**quality** | **string** |  |
**credits_used** | **int** | Text credits only. 0 while the image credit pool is on; &#x60;count × credit_weight&#x60; when it is switched off. |
**credits_remaining** | **int** | Text credits left this billing cycle (null &#x3D; no limit). | [optional]
**image_credits_used** | **int** | Image credits this call spent (1 per image; 0 when the image credit pool is switched off). |
**image_credits_remaining** | **int** | Image credits left this month (null &#x3D; no limit, or the image credit pool is switched off). |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
