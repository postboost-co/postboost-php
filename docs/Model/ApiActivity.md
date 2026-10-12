# # ApiActivity

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **int** |  |
**user_id** | **int** |  | [optional]
**token_ref** | **string** | First 12 hex characters of the SHA-256 of the API token used, to tell tokens apart. | [optional]
**client** | **string** | &#x60;X-PostBoost-Client&#x60; header, else the &#x60;User-Agent&#x60;. | [optional]
**route_name** | **string** |  | [optional]
**method** | **string** |  |
**post_uuid** | **string** |  | [optional]
**outcome** | [**\PostBoostClient\Model\ApiActivityOutcome**](ApiActivityOutcome.md) |  |
**http_status** | **int** |  |
**created_at** | **\DateTime** |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
