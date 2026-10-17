# # FreeToolPlanPostingFrequencyResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**posts_per_week_capacity** | **int** |  | [optional]
**sum_of_minimums** | **int** | The recommended minimums of the chosen networks added up. | [optional]
**networks** | [**\PostBoostClient\Model\FreeToolPlanPostingFrequencyResponseNetworksInner[]**](FreeToolPlanPostingFrequencyResponseNetworksInner.md) | One row per chosen network, in a fixed network order. | [optional]
**slots** | [**\PostBoostClient\Model\FreeToolPlanPostingFrequencyResponseSlotsInner[]**](FreeToolPlanPostingFrequencyResponseSlotsInner.md) | The weekly grid: each network&#39;s posts spread evenly from Monday, sorted by day. | [optional]
**warnings** | **string[]** |  | [optional]
**last_verified** | **\DateTime** | When the ranges were last checked against their sources. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
