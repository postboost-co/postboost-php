# # MentionIdentityInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider** | **string** | Mention provider key. One identity per provider. |
**handle** | **string** | Profile handle; a leading &#x60;@&#x60; is stripped. |
**label** | **string** |  | [optional]
**token** | **string** | Sealed lookup result that names the profile&#39;s network ID. | [optional]
**account_uuid** | **string** | A connected account of this workspace that names the profile. Wins over &#x60;token&#x60; when both are sent. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
