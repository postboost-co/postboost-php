# # Workspace

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | **string** |  |
**name** | **string** |  |
**hex_color** | **string** | Deprecated. Workspaces no longer have a colour (workspaces now use &#x60;avatar&#x60;); the API returns the constant &#x60;4f46e5&#x60; so existing clients keep working. Will be removed in API v2. | [optional]
**avatar** | **string** | URL of the workspace avatar, or null when none is set. Supersedes &#x60;hex_color&#x60;. | [optional]
**owner** | [**\PostBoostClient\Model\User**](User.md) |  | [optional]
**access_status** | **string** |  |
**created_at** | **string** | Display string in the configured timezone and clock: &#x60;M j, H:i&#x60; this year, &#x60;M j, Y, H:i&#x60; otherwise (12-hour setting: &#x60;h:ia&#x60;), not RFC 3339. |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
