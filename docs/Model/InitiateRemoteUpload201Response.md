# # InitiateRemoteUpload201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**uuid** | **string** |  |
**name** | **string** |  |
**mime_type** | **string** |  |
**type** | **string** |  |
**url** | **string** |  |
**thumb_url** | **string** |  | [optional]
**is_video** | **bool** |  |
**is_processing** | **bool** | True while an uploaded video is still being converted. | [optional]
**width** | **int** | Width in pixels, when stored. | [optional]
**height** | **int** | Height in pixels, when stored. | [optional]
**duration_ms** | **int** | Video duration in milliseconds; null for images or videos not read yet. | [optional]
**size** | **int** | File size in bytes. | [optional]
**alt_text** | **string** |  | [optional]
**folder** | [**\PostBoostClient\Model\MediaFolderRef**](MediaFolderRef.md) |  | [optional]
**created_at** | **\DateTime** |  |
**download_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
