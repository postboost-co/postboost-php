# # FreeToolGenerateYoutubeDescriptionRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **string** | What the video is about: a summary or the main points. |
**keywords** | **string** | Optional search keywords to use naturally, comma separated. | [optional]
**chapters** | **bool** | Add a chapters block after the first paragraph. | [optional] [default to false]
**chapter_lines** | **string[]** | Your chapters as &#x60;m:ss Title&#x60; lines, the first at 0:00. Used verbatim when &#x60;chapters&#x60; is true; without them the block has fill-in placeholders. Timestamps are never generated. | [optional]
**cta** | **string** | The closing call to action: subscribe, link (a [link] placeholder) or none. | [optional] [default to 'subscribe']
**workspace** | **string** | UUID of the workspace whose AI credits pay for the call. Default: your active workspace (a scoped API key: its own workspace). | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
