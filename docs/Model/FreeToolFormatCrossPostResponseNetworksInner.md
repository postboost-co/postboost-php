# # FreeToolFormatCrossPostResponseNetworksInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | **string** |  | [optional]
**label** | **string** |  | [optional]
**limit** | **int** |  | [optional]
**count** | **int** | Length as the network counts it. | [optional]
**fits** | **bool** |  | [optional]
**over_by** | **int** | Characters over the limit; 0 when it fits. | [optional]
**links** | **int** | Unique http(s) links in the text (trailing punctuation trimmed), as Threads counts them. | [optional]
**warnings** | [**\PostBoostClient\Model\FreeToolCheckPostResponseNetworksInnerErrorsInner[]**](FreeToolCheckPostResponseNetworksInnerErrorsInner.md) | Codes: threads_too_many_links, cut_by_fold, mentions_not_portable. | [optional]
**thread** | [**\PostBoostClient\Model\FreeToolFormatCrossPostResponseNetworksInnerThreadInner[]**](FreeToolFormatCrossPostResponseNetworksInnerThreadInner.md) | The thread for a text that does not fit (X, Threads, Bluesky, Mastodon); null when it fits or on LinkedIn. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
