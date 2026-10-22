# # FreeToolGenerateSocialPostsFromVideoRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **string** | The captions of your video: an .srt or .vtt file&#39;s text, or the text of YouTube&#39;s \&quot;Show transcript\&quot; panel. Timestamps, cue numbers and sound tags like [Music] are removed; 100 to 24,000 characters must remain. |
**video_url** | **string** | The video&#39;s YouTube link (watch, youtu.be, Shorts or live). Each output links it once, the X thread in its last post; without it the posts have no link. | [optional]
**title** | **string** | The video&#39;s title, as context for the posts. | [optional]
**outputs** | **string[]** | What to write, 1 to 4 different keys. | [optional]
**tone** | **string** |  | [optional] [default to 'friendly']
**workspace** | **string** | UUID of the workspace whose AI credits pay for the call. Default: your active workspace (a scoped API key: its own workspace). | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
