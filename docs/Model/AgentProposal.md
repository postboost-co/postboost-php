# # AgentProposal

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  |
**run_uuid** | **string** |  | [optional]
**post_uuid** | **string** |  | [optional]
**account_id** | **int** |  | [optional]
**kind** | **string** | &#x60;hold_post&#x60; moves the post back to draft; &#x60;edit_caption&#x60; replaces one caption. |
**severity** | **string** |  |
**reason** | **string** |  |
**payload** | **array<string,mixed>** | The proposed change. &#x60;hold_post&#x60;: &#x60;reasons[]&#x60; (&#x60;code&#x60;, &#x60;account_id&#x60;, &#x60;message&#x60;, &#x60;severity&#x60;) and &#x60;scheduled_at&#x60;. &#x60;edit_caption&#x60;: &#x60;version_account_id&#x60; (0 &#x3D; original), &#x60;item_index&#x60;, &#x60;before&#x60;, &#x60;after&#x60;. Both carry &#x60;post_updated_at&#x60;. |
**status** | **string** |  |
**decided_at** | **\DateTime** |  | [optional]
**applied_at** | **\DateTime** |  | [optional]
**note** | **string** |  | [optional]
**error** | **string** | Why a proposal went stale or failed. | [optional]
**created_at** | **\DateTime** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
