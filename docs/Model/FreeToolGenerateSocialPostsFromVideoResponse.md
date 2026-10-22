# # FreeToolGenerateSocialPostsFromVideoResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**outputs** | [**\PostBoostClient\Model\FreeToolGenerateSocialPostsFromVideoResponseOutputs**](FreeToolGenerateSocialPostsFromVideoResponseOutputs.md) |  | [optional]
**outputs_skipped** | **string[]** | Requested outputs that came back empty: generate again to get them. | [optional]
**warnings** | **string[]** | What to know before posting, in plain words. | [optional]
**video_url** | **string** | The normalised video link the posts use, or null. | [optional]
**cleaned_chars** | **int** | Characters of caption text left after cleaning; the model read these. | [optional]
**removed_timestamps** | **bool** | True when timestamps, cue numbers, tags or repeated caption lines were removed. | [optional]
**credits_spent** | **int** | AI credits this call took from the workspace: 1, or 0 for a cached result. | [optional]
**cached** | **bool** | True when the same request was answered before (free). | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
