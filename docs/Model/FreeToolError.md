# # FreeToolError

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**message** | **string** |  |
**retry_after** | **int** | 429 only: seconds until the limit resets. | [optional]
**code** | **string** | 429 of a paid AI tool: &#x60;ai_credits_exhausted&#x60;. | [optional]
**register_url** | **string** | 429 for guests: sign up for a token with higher limits. 401 of a paid AI tool: sign up for a token. | [optional]
**upgrade_url** | **string** | 429 when a token user reached the plan&#39;s daily cap, or a paid AI tool&#39;s workspace has no AI credits left. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
