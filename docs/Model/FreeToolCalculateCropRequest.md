# # FreeToolCalculateCropRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**width** | **int** | Source image width in pixels. |
**height** | **int** | Source image height in pixels. |
**network** | **string** | Network key from getImageSizes (&#x60;network_key&#x60;), e.g. &#x60;instagram&#x60;. With &#x60;format&#x60;, picks the target size. | [optional]
**format** | **string** | Format key from getImageSizes (&#x60;format_key&#x60;), e.g. &#x60;feed-square&#x60;. | [optional]
**target_width** | **int** | Target width in pixels, instead of &#x60;network&#x60; + &#x60;format&#x60;. | [optional]
**target_height** | **int** | Target height in pixels, instead of &#x60;network&#x60; + &#x60;format&#x60;. | [optional]
**fit** | **string** | &#x60;cover&#x60; crops to fill the target; &#x60;contain&#x60; keeps the whole image and centres it. | [optional] [default to 'cover']

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
