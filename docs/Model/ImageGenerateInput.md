# # ImageGenerateInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**caption** | **string** | Social media caption. Triggers standard mode. Takes priority over prompt. | [optional]
**platform** | **string** | Required when caption is provided. | [optional]
**template** | **string** |  | [optional]
**style** | **string** |  | [optional]
**brand_voice** | **string** |  | [optional]
**custom_instructions** | **string** |  | [optional]
**prompt** | **string** | Developer escape hatch. Bypasses internal prompt builder. Ignored if caption is present. | [optional]
**aspect_ratio** | **string** |  | [optional] [default to '1:1']
**count** | **int** |  | [optional] [default to 1]
**quality** | **string** |  | [optional] [default to 'standard']

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
