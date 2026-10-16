# # FreeToolGenerateSocialPostsFromBlogRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | **string** | Public http(s) address of the blog post. Give &#x60;url&#x60; or &#x60;text&#x60;. | [optional]
**text** | **string** | The blog post itself, instead of &#x60;url&#x60;. | [optional]
**platforms** | **string[]** | Networks to write for, at most 4 per call (one AI credit each). |
**tone** | **string** |  | [optional] [default to 'casual']
**length** | **string** |  | [optional] [default to 'short']
**hashtags** | **string** | How many hashtags to include. | [optional] [default to 'no']
**cta** | **string** | Call to action to end with. | [optional] [default to 'no']
**workspace** | **string** | UUID of the workspace whose AI credits pay for the call. Default: your active workspace (a scoped API key: its own workspace). | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
