# # FreeToolCalculateSmmPricingRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**networks** | **int** | Number of social networks managed. |
**posts_per_week** | **int** | Posts per week on each network. |
**content_type** | **string** | What goes into a post. Assumed minutes per post: copy 30, copy_design 60, copy_design_video 120. | [optional] [default to 'copy_design']
**community_hours_per_week** | **float** | Community management (replies, comments, DMs), hours per week. | [optional] [default to 0]
**reporting_hours_per_month** | **float** | Reporting, hours per month. | [optional] [default to 0]
**ad_hours_per_month** | **float** | Paid social ad management, hours per month. | [optional] [default to 0]
**hourly_rate** | **float** | Your hourly rate. The default 50 is a round placeholder, not a market rate. | [optional] [default to 50]
**currency** | **string** | Currency for formatting only; nothing is converted. | [optional] [default to 'USD']
**pricing_model** | **string** | Which price leads the quote: hourly, monthly retainer or per post. | [optional] [default to 'retainer']

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
