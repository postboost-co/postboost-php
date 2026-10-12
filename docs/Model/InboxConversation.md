# # InboxConversation

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **string** | Conversation UUID. |
**provider** | **string** |  |
**type** | **string** |  | [optional]
**status** | **string** |  |
**unread** | **bool** |  |
**sentiment** | **string** |  | [optional]
**ai_label** | **string** |  | [optional]
**is_spam** | **bool** |  | [optional]
**is_hidden** | **bool** |  | [optional]
**provider_post_id** | **string** |  | [optional]
**account** | [**\PostBoostClient\Model\InboxConversationAccount**](InboxConversationAccount.md) |  | [optional]
**author** | [**\PostBoostClient\Model\InboxMessageAuthor**](InboxMessageAuthor.md) |  | [optional]
**latest_message** | **object** | Only in lists. | [optional]
**messages** | [**\PostBoostClient\Model\InboxMessage[]**](InboxMessage.md) | Only on &#x60;GET inbox/conversations/{conversationId}&#x60;. | [optional]
**last_message_at** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
