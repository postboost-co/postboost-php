# # FreeToolCalculateSocialRoiResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**period** | **string** |  | [optional]
**revenue** | **float** |  | [optional]
**total_cost** | **float** | Sum of every cost, labor &#x3D; hours × hourly rate. 2 decimals. | [optional]
**net_return** | **float** | Revenue minus total cost. 2 decimals. | [optional]
**roi_percent** | **float** | (revenue − total cost) ÷ total cost × 100, 1 decimal; null when the total cost is 0. | [optional]
**cost_breakdown** | [**\PostBoostClient\Model\FreeToolCalculateSocialRoiResponseCostBreakdownInner[]**](FreeToolCalculateSocialRoiResponseCostBreakdownInner.md) | Every cost above 0, with its share of the total cost (percent, 1 decimal). | [optional]
**warnings** | **string[]** |  | [optional]
**formula** | **string** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
