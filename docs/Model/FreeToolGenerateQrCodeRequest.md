# # FreeToolGenerateQrCodeRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | **string** | The link or text to encode. |
**utm** | [**\PostBoostClient\Model\FreeToolGenerateQrCodeRequestUtm**](FreeToolGenerateQrCodeRequestUtm.md) |  | [optional]
**error_correction** | **string** | How much of the code can be damaged and still scan: L 7%, M 15%, Q 25%, H 30%. | [optional] [default to 'M']
**size** | **int** | Width and height of the SVG in pixels. | [optional] [default to 512]
**foreground** | **string** | Colour of the modules, #RRGGBB. | [optional] [default to '#000000']
**background** | **string** | Background colour, #RRGGBB. | [optional] [default to '#FFFFFF']

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
