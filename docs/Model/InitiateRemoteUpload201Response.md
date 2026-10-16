# # InitiateRemoteUpload201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Numeric media id, returned as a string (the engine casts it). Use &#x60;uuid&#x60; to address media in the API. |
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
**created_at** | **string** | &#x60;Y-m-d H:i:s&#x60; in UTC (not RFC 3339). |
**download_id** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
