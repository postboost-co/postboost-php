# # PostingSchedule

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **int** | The account asked for; 0 for the workspace schedule. |
**source_account_id** | **int** | Whose schedule applies; 0 when the workspace schedule applies. |
**inherited** | **bool** | True when the account follows the workspace schedule. |
**timezone** | **string** |  |
**auto_tune** | **bool** | Adjust times automatically from engagement data. |
**times** | [**\PostBoostClient\Model\PostingScheduleDay[]**](PostingScheduleDay.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
