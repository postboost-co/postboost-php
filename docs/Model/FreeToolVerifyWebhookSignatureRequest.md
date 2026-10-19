# # FreeToolVerifyWebhookSignatureRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**body** | **string** | The raw request body exactly as received (up to 64 KB). Use a test payload, not production data. |
**secret** | **string** | The webhook secret. Use a test secret: never send a production secret to any third-party service. |
**signature** | **string** | The received signature header value, e.g. X-Signature. |
**algorithm** | **string** |  | [optional] [default to 'sha256']
**encoding** | **string** |  | [optional] [default to 'hex']
**prefix** | **string** | A prefix the sender puts before the signature, e.g. \&quot;sha256&#x3D;\&quot; (GitHub). | [optional] [default to '']

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
