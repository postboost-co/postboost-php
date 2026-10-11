# # AccountAnalytics

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account** | [**\PostBoostClient\Model\Account**](Account.md) |  |
**type** | **string** | The analytics tab returned. |
**tabs** | **string[]** | Tabs this account supports; any of them can be passed as &#x60;type&#x60;. |
**period** | [**\PostBoostClient\Model\AnalyticsPeriod**](AnalyticsPeriod.md) |  |
**initial_sync** | [**\PostBoostClient\Model\AccountAnalyticsInitialSync**](AccountAnalyticsInitialSync.md) |  |
**data** | **array<string,mixed>** | Provider- and tab-specific metrics. Chart series are lists of &#x60;{date, value}&#x60; points. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
