# # FreeToolCalculateCarouselSlicesResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**slides** | [**\PostBoostClient\Model\FreeToolCalculateCarouselSlicesResponseSlidesInner[]**](FreeToolCalculateCarouselSlicesResponseSlidesInner.md) | The part of the source image each slide shows, left to right, in source pixels. | [optional]
**output** | [**\PostBoostClient\Model\FreeToolCalculateCarouselSlicesResponseOutput**](FreeToolCalculateCarouselSlicesResponseOutput.md) |  | [optional]
**scale** | **float** | Output pixels per source pixel, 4 decimals. | [optional]
**upscaled** | **bool** | True when the source is enlarged (scale above 1), which can look soft. | [optional]
**warnings** | **string[]** | Upscaling and how much of the source is cropped away. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
