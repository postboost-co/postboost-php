# # FreeToolCalculateSmmPricingResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**currency** | **string** |  | [optional]
**pricing_model** | **string** |  | [optional]
**posts_per_month** | **float** | Networks × posts per week × 52 ÷ 12, 1 decimal. | [optional]
**hours_per_month** | **float** | Estimated working hours a month, 1 decimal. | [optional]
**hourly_rate** | **float** |  | [optional]
**monthly_retainer** | **float** | Hours a month × hourly rate, whole currency units. | [optional]
**per_post** | **float** | Monthly retainer ÷ posts a month, 2 decimals; null with no posts. | [optional]
**range** | [**\PostBoostClient\Model\FreeToolCalculateSmmPricingResponseRange**](FreeToolCalculateSmmPricingResponseRange.md) |  | [optional]
**line_items** | [**\PostBoostClient\Model\FreeToolCalculateSmmPricingResponseLineItemsInner[]**](FreeToolCalculateSmmPricingResponseLineItemsInner.md) | Every task with hours above 0. | [optional]
**assumptions** | **string[]** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
