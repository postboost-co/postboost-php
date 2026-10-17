# # FreeToolPlanPostingFrequencyResponseNetworksInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**network** | **string** |  | [optional]
**label** | **string** |  | [optional]
**recommended_per_week** | [**\PostBoostClient\Model\FreeToolPlanPostingFrequencyResponseNetworksInnerRecommendedPerWeek**](FreeToolPlanPostingFrequencyResponseNetworksInnerRecommendedPerWeek.md) |  | [optional]
**recommended_label** | **string** | The range as text, e.g. \&quot;3-5 per week\&quot; or \&quot;1+ per week\&quot;. | [optional]
**allocated_per_week** | **int** | Your posts for this network: capacity split in proportion to the range midpoints (the minimum for an open-ended range). | [optional]
**fit** | **string** | Where the allocation sits against the recommended range. | [optional]
**source_type** | **string** | measured &#x3D; a study of real posts; vendor &#x3D; a software vendor&#39;s guidance; platform &#x3D; the network&#39;s own guidance. | [optional]
**sources** | [**\PostBoostClient\Model\FreeToolPlanPostingFrequencyResponseNetworksInnerSourcesInner[]**](FreeToolPlanPostingFrequencyResponseNetworksInnerSourcesInner.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
