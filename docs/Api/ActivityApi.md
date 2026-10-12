# PostBoostClient\ActivityApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**listApiActivity()**](ActivityApi.md#listApiActivity) | **GET** /{workspaceUuid}/activity | List API activity |


## `listApiActivity()`

```php
listApiActivity($workspace_uuid, $outcome, $client, $since, $page): \PostBoostClient\Model\ListApiActivity200Response
```

List API activity

Every write request (`POST`, `PUT`, `DELETE`) made through the API in this workspace, newest first, with the client that made it and its outcome. Kept for 90 days. Send an `X-PostBoost-Client` header (for example `my-agent/1.2`) to label your requests; otherwise the `User-Agent` is recorded.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\ActivityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$outcome = new \PostBoostClient\Model\\PostBoostClient\Model\ApiActivityOutcome(); // \PostBoostClient\Model\ApiActivityOutcome
$client = 'client_example'; // string | Client label prefix, for example `mcp`.
$since = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Only entries at or after this time (UTC).
$page = 1; // int

try {
    $result = $apiInstance->listApiActivity($workspace_uuid, $outcome, $client, $since, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ActivityApi->listApiActivity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **outcome** | [**\PostBoostClient\Model\ApiActivityOutcome**](../Model/.md)|  | [optional] |
| **client** | **string**| Client label prefix, for example &#x60;mcp&#x60;. | [optional] |
| **since** | **\DateTime**| Only entries at or after this time (UTC). | [optional] |
| **page** | **int**|  | [optional] [default to 1] |

### Return type

[**\PostBoostClient\Model\ListApiActivity200Response**](../Model/ListApiActivity200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
