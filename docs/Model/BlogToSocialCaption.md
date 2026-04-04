# # BlogToSocialCaption

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **int** | ID of the social account this caption was generated for. | [optional]
**provider** | **string** | Social media platform identifier. | [optional]
**content** | **string** | The generated caption text. &#x60;null&#x60; if generation failed for this account. | [optional]
**character_count** | **int** | Character count of the generated content. &#x60;null&#x60; if generation failed. | [optional]
**character_limit** | **int** | Maximum allowed character count for this platform. | [optional]
**error** | **string** | Error message if caption generation failed for this account. &#x60;null&#x60; on success. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
