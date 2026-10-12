# # AccountHealth

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**uuid** | **string** |  |
**name** | **string** |  |
**provider** | **string** |  |
**authorized** | **bool** | False when the account must be reconnected. |
**has_token** | **bool** | Whether an access token is stored for the account. |
**healthy** | **bool** | &#x60;authorized&#x60; and &#x60;has_token&#x60;: the account can publish. |
**daily_cap** | [**\PostBoostClient\Model\AccountHealthDailyCap**](AccountHealthDailyCap.md) |  |
**connection** | [**\PostBoostClient\Model\AccountConnectionHealth**](AccountConnectionHealth.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
