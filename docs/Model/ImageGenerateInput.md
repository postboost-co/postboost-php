# # ImageGenerateInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**caption** | **string** | Social media caption. Triggers standard mode. Takes priority over prompt. | [optional]
**platform** | **string** | Required when caption is provided. | [optional]
**template** | **string** |  | [optional]
**style** | **string** |  | [optional]
**brand_voice** | **string** | Free-text tone for the image. When sent, it replaces the stored workspace brand voice for this call. | [optional]
**use_brand_voice** | **bool** | When &#x60;brand_voice&#x60; is not sent, derive the image tone from the workspace brand voice. Ignored in developer mode (&#x60;prompt&#x60;). | [optional] [default to true]
**custom_instructions** | **string** |  | [optional]
**prompt** | **string** | Developer escape hatch. Bypasses internal prompt builder. Ignored if caption is present. | [optional]
**aspect_ratio** | **string** |  | [optional] [default to '1:1']
**count** | **int** |  | [optional] [default to 1]
**quality** | **string** |  | [optional] [default to 'standard']

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
