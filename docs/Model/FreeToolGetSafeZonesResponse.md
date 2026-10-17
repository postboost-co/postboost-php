# # FreeToolGetSafeZonesResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**platform** | **string** |  | [optional]
**label** | **string** | Platform name. | [optional]
**width** | **int** |  | [optional]
**height** | **int** |  | [optional]
**unsafe_areas** | [**\PostBoostClient\Model\FreeToolGetSafeZonesResponseUnsafeAreasInner[]**](FreeToolGetSafeZonesResponseUnsafeAreasInner.md) | Areas the app&#39;s UI usually covers, in frame pixels from the top-left corner. Edges are scaled from 1080 × 1920 and rounded to the nearest pixel (halves up), so neighbouring boxes stay edge to edge. | [optional]
**safe_area** | [**\PostBoostClient\Model\FreeToolGetSafeZonesResponseSafeArea**](FreeToolGetSafeZonesResponseSafeArea.md) |  | [optional]
**source** | [**\PostBoostClient\Model\FreeToolGetSafeZonesResponseSource**](FreeToolGetSafeZonesResponseSource.md) |  | [optional]
**last_verified** | **string** | Date the sources were last checked (YYYY-MM-DD). | [optional]
**caveat** | **string** |  | [optional]
**warnings** | **string[]** | Set when the frame is not 9:16, so the boxes are stretched. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
