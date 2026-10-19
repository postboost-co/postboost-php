# # FreeToolBuildHashtagGroupsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hashtags** | **string[]** | Clean hashtags in input order, duplicates removed. | [optional]
**removed** | [**\PostBoostClient\Model\FreeToolBuildHashtagGroupsResponseRemovedInner[]**](FreeToolBuildHashtagGroupsResponseRemovedInner.md) | Entries that were dropped, with the reason. | [optional]
**cap** | **int** | Hashtags PostBoost allows per post on the network; null &#x3D; no hard limit. | [optional]
**group_size** | **int** | Hashtags per group that was used. | [optional]
**groups** | [**\PostBoostClient\Model\FreeToolBuildHashtagGroupsResponseGroupsInner[]**](FreeToolBuildHashtagGroupsResponseGroupsInner.md) |  | [optional]
**over_cap** | **bool** | A group holds more hashtags than the cap. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
