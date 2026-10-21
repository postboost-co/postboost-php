# # FreeToolBuildAgentSkillResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**format** | **string** |  | [optional]
**filename** | **string** |  | [optional]
**content** | **string** | The file, in Markdown. | [optional]
**install** | **string[]** | Where to put the file. | [optional]
**tools_used** | **string[]** | The connector tool names the content names, in first-appearance order; empty with api_token. | [optional]
**lines** | **int** |  | [optional]
**warnings** | [**\PostBoostClient\Model\FreeToolCheckPostResponseNetworksInnerErrorsInner[]**](FreeToolCheckPostResponseNetworksInnerErrorsInner.md) | Codes: name_normalized, task_limited_by_autonomy, autonomy_high, too_long. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
