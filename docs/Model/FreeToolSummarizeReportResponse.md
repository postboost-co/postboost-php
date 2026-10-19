# # FreeToolSummarizeReportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**posts** | **int** |  | [optional]
**date_range** | [**\PostBoostClient\Model\FreeToolSummarizeReportResponseDateRange**](FreeToolSummarizeReportResponseDateRange.md) |  | [optional]
**views** | **int** |  | [optional]
**engagements** | **int** |  | [optional]
**engagement_rate** | **float** | Percent, 2 decimals; null without views. | [optional]
**engagements_from** | **string[]** | The counts added up as engagements. | [optional]
**networks** | [**\PostBoostClient\Model\FreeToolSummarizeReportResponseNetworksInner[]**](FreeToolSummarizeReportResponseNetworksInner.md) |  | [optional]
**top_posts** | [**\PostBoostClient\Model\FreeToolSummarizeReportResponseTopPostsInner[]**](FreeToolSummarizeReportResponseTopPostsInner.md) |  | [optional]
**weekdays** | [**\PostBoostClient\Model\FreeToolSummarizeReportResponseWeekdaysInner[]**](FreeToolSummarizeReportResponseWeekdaysInner.md) |  | [optional]
**best_weekday** | **string** | The weekday with the highest average engagements per post. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
