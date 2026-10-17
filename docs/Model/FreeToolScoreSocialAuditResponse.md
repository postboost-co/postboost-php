# # FreeToolScoreSocialAuditResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**score** | **int** | Overall score: all points over the maximum, as 0-100 rounded half up. | [optional]
**networks** | [**\PostBoostClient\Model\FreeToolScoreSocialAuditResponseNetworksInner[]**](FreeToolScoreSocialAuditResponseNetworksInner.md) | One row per audited network, in a fixed network order. | [optional]
**top_fixes** | [**\PostBoostClient\Model\FreeToolScoreSocialAuditResponseTopFixesInner[]**](FreeToolScoreSocialAuditResponseTopFixesInner.md) | Up to 3 questions with the fewest points over all audited networks (ties: checklist order); only questions answered below yes somewhere. | [optional]
**report_markdown** | **string** | The scorecard as a Markdown report: overall score, top fixes and every answer per network. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
