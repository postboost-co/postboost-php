# # PostingTimes

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**has_data** | **bool** |  |
**timezone** | **string** |  |
**offset_hours** | **int** |  |
**accounts** | **int** | Accounts that contributed scores. |
**samples** | **int** |  |
**days** | [**\PostBoostClient\Model\PostingTimesDaysInner[]**](PostingTimesDaysInner.md) | One entry per weekday (&#x60;day&#x60; 0 &#x3D; Sunday). |
**day_intervals** | **\PostBoostClient\Model\PostingTimesDayIntervalsInnerInner[][]** | Per weekday, 2-hour intervals. |
**best** | [**\PostBoostClient\Model\PostingTimesBestInner[]**](PostingTimesBestInner.md) | Up to three recommended slots, at most one per weekday. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
