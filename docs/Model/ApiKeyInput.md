# # ApiKeyInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **string** |  |
**abilities** | [**\PostBoostClient\Model\ApiKeyAbility[]**](ApiKeyAbility.md) |  |
**account_ids** | **int[]** | Limit the key to these account ids of the workspace. Omit or null for every account. A limited key must send &#x60;account_ids&#x60; on recycling rules, report exports and AI drafts, and its lists show only its accounts. | [optional]
**expires_at** | **\DateTime** | Last day the key works. Must be after today. Omit for no expiry. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
