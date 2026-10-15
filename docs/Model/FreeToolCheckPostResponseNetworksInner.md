# # FreeToolCheckPostResponseNetworksInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | **string** |  | [optional]
**label** | **string** |  | [optional]
**ok** | **bool** | False when an error would stop the post from publishing. | [optional]
**count** | **int** | Characters as this network counts them. | [optional]
**limit** | **int** |  | [optional]
**errors** | [**\PostBoostClient\Model\FreeToolCheckPostResponseNetworksInnerErrorsInner[]**](FreeToolCheckPostResponseNetworksInnerErrorsInner.md) | Codes: too_long, too_many_hashtags, media_required, too_many_media, media_type, video_too_long, video_too_short. | [optional]
**warnings** | [**\PostBoostClient\Model\FreeToolCheckPostResponseNetworksInnerErrorsInner[]**](FreeToolCheckPostResponseNetworksInnerErrorsInner.md) | Codes: cut_by_fold, link_not_clickable. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
