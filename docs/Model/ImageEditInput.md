# # ImageEditInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**media_uuid** | **string** | UUID of the source media item to edit |
**prompt** | **string** | Describe what to change in the image |
**mask_uuid** | **string** | UUID of a mask image. Transparent areas will be edited. | [optional]
**use_brand_voice** | **bool** | Append the workspace brand voice&#39;s visual tone to the edit prompt. Off by default because edits are literal instructions. | [optional] [default to false]
**aspect_ratio** | **string** |  | [optional] [default to '1:1']
**count** | **int** |  | [optional] [default to 1]
**quality** | **string** |  | [optional] [default to 'standard']

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
