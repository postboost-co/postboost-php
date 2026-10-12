# # ReportExportInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**format** | **string** |  |
**dataset** | **string** | CSV rows; default &#x60;posts&#x60;. Ignored for PDF. | [optional]
**period** | **string** | Default &#x60;last_month&#x60;. Ignored when &#x60;date_from&#x60; and &#x60;date_to&#x60; are sent. | [optional]
**date_from** | **\DateTime** |  | [optional]
**date_to** | **\DateTime** | At most 366 days after &#x60;date_from&#x60;. | [optional]
**account_ids** | **int[]** | Limit the report to these accounts; default all. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
