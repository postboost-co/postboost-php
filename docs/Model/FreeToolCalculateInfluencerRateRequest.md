# # FreeToolCalculateInfluencerRateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**network** | **string** | LinkedIn is not offered: no primary source for its rates. |
**followers** | **int** | Followers (subscribers on YouTube). Sets the tier. |
**deliverable** | **string** | Instagram: post (default), reel, carousel. TikTok: video. X and Facebook: post. YouTube: integration (default), dedicated, short. | [optional]
**avg_views** | **int** | Expected views of the deliverable. Required on YouTube, which is priced per 1,000 views; with cpm_usd it gives your own CPM estimate on any network. | [optional]
**cpm_usd** | **int** | Your own price per 1,000 views, in whole USD, for the CPM estimate. | [optional]
**usage_rights_months** | **int** | Months the brand may reuse the content. | [optional] [default to 0]
**exclusivity** | **bool** | The creator agrees not to work with competitors for the campaign. | [optional] [default to false]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
