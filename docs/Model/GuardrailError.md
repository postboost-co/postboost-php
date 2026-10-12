# # GuardrailError

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**message** | **string** |  |
**code** | **string** |  | [optional]
**account_id** | **int** | The account the problem is about. | [optional]
**existing_post_uuid** | **string** | &#x60;duplicate_post&#x60; only: the earlier post with the same content. | [optional]
**limit** | **int** | &#x60;account_daily_cap_reached&#x60; only: the account&#39;s daily cap. | [optional]
**used** | **int** | &#x60;account_daily_cap_reached&#x60; only: posts already counted on that UTC day. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
