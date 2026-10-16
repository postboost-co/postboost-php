# # FreeToolCalculateAspectRatioResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ratio** | **string** | Simplified ratio, e.g. &#x60;4:5&#x60;. Decimal ratios stay as given. | [optional]
**decimal** | **float** | Width divided by height, 4 decimals. | [optional]
**width** | **int** |  | [optional]
**height** | **int** |  | [optional]
**rounding** | [**\PostBoostClient\Model\FreeToolCalculateAspectRatioResponseRounding**](FreeToolCalculateAspectRatioResponseRounding.md) |  | [optional]
**orientation** | **string** |  | [optional]
**matches** | [**\PostBoostClient\Model\FreeToolCalculateAspectRatioResponseMatchesInner[]**](FreeToolCalculateAspectRatioResponseMatchesInner.md) | Social media image presets with the same ratio, else the nearest. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
