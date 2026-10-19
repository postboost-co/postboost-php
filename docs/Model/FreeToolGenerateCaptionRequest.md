# # FreeToolGenerateCaptionRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **string** | What the post is about. |
**tone** | **string** |  | [optional] [default to 'friendly']
**length** | **string** | short: 10-20 words, medium: 25-40, long: 45-60. | [optional] [default to 'medium']
**emoji** | **bool** | Use a few fitting emoji. | [optional] [default to true]
**hashtags** | **bool** | End each caption with 3-5 relevant hashtags. | [optional] [default to false]
**network** | **string** | The network the text is written for. | [optional] [default to 'instagram']
**workspace** | **string** | UUID of the workspace whose AI credits pay for the call. Default: your active workspace (a scoped API key: its own workspace). | [optional]
**format** | **string** | caption: short captions (default). post: long-form posts of 300-600, 600-1,300 or 1,300-2,000 characters by &#x60;length&#x60;, with at most 3 hashtags; network linkedin only. | [optional] [default to 'caption']

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
