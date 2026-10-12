# # InboxReplyDraft

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Draft UUID. |
**status** | **string** |  |
**body** | **string** |  |
**source** | **string** |  |
**conversation_id** | **string** |  | [optional]
**provider** | **string** |  | [optional]
**in_reply_to** | **object** | The incoming message this replies to (same shape as &#x60;InboxMessage&#x60;). | [optional]
**created_by** | **string** | Name of the user whose API key wrote the draft. | [optional]
**reviewed_by** | **string** |  | [optional]
**reviewed_at** | **\DateTime** |  | [optional]
**sent_message_id** | **string** | The sent reply&#39;s message UUID, once sent. | [optional]
**error** | **string** | Why sending failed. | [optional]
**created_at** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
