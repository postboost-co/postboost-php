# # FreeToolCalculateXApiCostResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**line_items** | [**\PostBoostClient\Model\FreeToolCalculateXApiCostResponseLineItemsInner[]**](FreeToolCalculateXApiCostResponseLineItemsInner.md) | One row per billed resource: count × unit price. | [optional]
**total_usd** | **float** | Sum of every line item. | [optional]
**link_premium_usd** | **float** | What the link posts cost on top of the plain post price. | [optional]
**notes** | **string[]** |  | [optional]
**prices_last_verified** | **\DateTime** | When the prices were last checked against the source. | [optional]
**source** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
