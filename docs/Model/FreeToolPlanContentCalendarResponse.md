# # FreeToolPlanContentCalendarResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**end_date** | **string** | Last day of the calendar (YYYY-MM-DD). | [optional]
**total** | **int** | Number of posts planned. | [optional]
**slots** | [**\PostBoostClient\Model\FreeToolPlanContentCalendarResponseSlotsInner[]**](FreeToolPlanContentCalendarResponseSlotsInner.md) |  | [optional]
**csv** | **string** | The calendar as CSV (UTF-8 with BOM): Date, Day, Time, Network, Pillar, Idea. | [optional]
**ics** | **string** | The calendar as an iCalendar file: one 15-minute event per post, in floating local time. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
