# # FreeToolGetVideoSpecsResponseSpecsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**network** | **string** | Network name. | [optional]
**network_key** | **string** | Key for &#x60;network&#x60;. | [optional]
**placement** | **string** | Placement; &#x60;(app)&#x60; and &#x60;(publishing API)&#x60; rows differ where the network says so. | [optional]
**placement_key** | **string** | Key for &#x60;placement&#x60;. | [optional]
**ratio** | **string** | Aspect ratios as the source states them. | [optional]
**resolution** | **string** | Resolution, frame rate and codec notes. | [optional]
**length** | **string** | Length limits. | [optional]
**max_size** | **string** | File size limit. | [optional]
**formats** | **string** | Container and codec formats. | [optional]
**safe_zone** | **string** | Text safe zone, only where the network publishes one. | [optional]
**basis** | **string** | &#x60;official&#x60; when the network itself states it, else how it was found. | [optional]
**sources** | **string[]** | URLs of the sources. | [optional]
**limits** | [**\PostBoostClient\Model\FreeToolGetVideoSpecsResponseSpecsInnerLimits**](FreeToolGetVideoSpecsResponseSpecsInnerLimits.md) |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
