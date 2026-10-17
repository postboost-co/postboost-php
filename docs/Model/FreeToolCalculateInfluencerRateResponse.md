# # FreeToolCalculateInfluencerRateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**tier** | **string** |  | [optional]
**tier_label** | **string** |  | [optional]
**deliverable** | **string** |  | [optional]
**guide_low** | **int** | USD, low end of the vendor price-guide range after the adjustments. | [optional]
**guide_high** | **int** | USD, high end; null when the guide is open-ended (e.g. 10,000+). | [optional]
**guide_source** | [**\PostBoostClient\Model\FreeToolCalculateInfluencerRateResponseGuideSource**](FreeToolCalculateInfluencerRateResponseGuideSource.md) |  | [optional]
**marketplace_median** | **int** | USD, the measured median paid deliverable for this tier, all networks, before adjustments. | [optional]
**marketplace_note** | **string** |  | [optional]
**marketplace_source** | [**\PostBoostClient\Model\FreeToolCalculateInfluencerRateResponseGuideSource**](FreeToolCalculateInfluencerRateResponseGuideSource.md) |  | [optional]
**cpm_estimate** | **int** | USD, avg_views / 1,000 × cpm_usd (half up); null without both. | [optional]
**multipliers** | [**\PostBoostClient\Model\FreeToolCalculateInfluencerRateResponseMultipliersInner[]**](FreeToolCalculateInfluencerRateResponseMultipliersInner.md) | Every adjustment applied, as a percent of the base price. | [optional]
**method** | **string** |  | [optional]
**warnings** | **string[]** |  | [optional]
**currency** | **string** |  | [optional]
**last_verified** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
