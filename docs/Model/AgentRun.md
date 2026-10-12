# # AgentRun

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  |
**agent_uuid** | **string** |  |
**agent_type** | **string** |  |
**trigger** | **string** |  |
**status** | **string** |  |
**started_at** | **\DateTime** |  | [optional]
**finished_at** | **\DateTime** |  | [optional]
**items_checked** | **int** |  |
**proposals_created** | **int** |  |
**credits_used** | **int** | AI credits this run used. |
**summary** | **string** |  | [optional]
**error** | **string** |  | [optional]
**created_at** | **\DateTime** |  | [optional]
**proposals** | [**\PostBoostClient\Model\AgentProposal[]**](AgentProposal.md) | Only on &#x60;GET /agent-runs/{runUuid}&#x60;. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
