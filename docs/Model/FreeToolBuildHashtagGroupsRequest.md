# # FreeToolBuildHashtagGroupsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **string** | Hashtags or words, separated by spaces, commas or new lines. A missing # is added. |
**network** | **string** | Network whose hashtag cap applies. | [optional] [default to 'instagram']
**group_size** | **int** | Hashtags per group. Default: the network&#39;s cap, or 5 when it has no hard cap. | [optional]
**case** | **string** | keep the first spelling of each hashtag, or lower-case all of them. | [optional] [default to 'keep']
**format** | **string** | inline: one line of tags. first_comment: five \&quot;.\&quot; lines, then the tags. | [optional] [default to 'inline']

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
