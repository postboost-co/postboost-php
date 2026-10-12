# PostBoostClient\CompetitorsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addCompetitor()**](CompetitorsApi.md#addCompetitor) | **POST** /{workspaceUuid}/competitors | Track a competitor |
| [**deleteCompetitor()**](CompetitorsApi.md#deleteCompetitor) | **DELETE** /{workspaceUuid}/competitors/{competitorId} | Stop tracking a competitor |
| [**getCompetitor()**](CompetitorsApi.md#getCompetitor) | **GET** /{workspaceUuid}/competitors/{competitorId} | Get a competitor |
| [**listCompetitors()**](CompetitorsApi.md#listCompetitors) | **GET** /{workspaceUuid}/competitors | List competitors |


## `addCompetitor()`

```php
addCompetitor($workspace_uuid, $competitor_input): \PostBoostClient\Model\AddCompetitor202Response
```

Track a competitor

Starts tracking a public Instagram business or creator account from one of your Instagram accounts (connected through a Facebook Page). Returns `202` at once; followers, snapshots and recent media appear after the background import. `409` if that account already tracks the username. Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\CompetitorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$competitor_input = new \PostBoostClient\Model\CompetitorInput(); // \PostBoostClient\Model\CompetitorInput

try {
    $result = $apiInstance->addCompetitor($workspace_uuid, $competitor_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->addCompetitor: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **competitor_input** | [**\PostBoostClient\Model\CompetitorInput**](../Model/CompetitorInput.md)|  | |

### Return type

[**\PostBoostClient\Model\AddCompetitor202Response**](../Model/AddCompetitor202Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteCompetitor()`

```php
deleteCompetitor($workspace_uuid, $competitor_id)
```

Stop tracking a competitor

Deletes the competitor with its snapshots and media. Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\CompetitorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$competitor_id = 56; // int | The competitor `id`.

try {
    $apiInstance->deleteCompetitor($workspace_uuid, $competitor_id);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->deleteCompetitor: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **competitor_id** | **int**| The competitor &#x60;id&#x60;. | |

### Return type

void (empty response body)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getCompetitor()`

```php
getCompetitor($workspace_uuid, $competitor_id): \PostBoostClient\Model\GetCompetitor200Response
```

Get a competitor

The competitor with daily follower snapshots for the last 90 days and its 12 most recent posts.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\CompetitorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$competitor_id = 56; // int | The competitor `id`.

try {
    $result = $apiInstance->getCompetitor($workspace_uuid, $competitor_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->getCompetitor: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **competitor_id** | **int**| The competitor &#x60;id&#x60;. | |

### Return type

[**\PostBoostClient\Model\GetCompetitor200Response**](../Model/GetCompetitor200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listCompetitors()`

```php
listCompetitors($workspace_uuid, $account_id): \PostBoostClient\Model\ListCompetitors200Response
```

List competitors

Instagram business or creator accounts the workspace tracks, by follower count.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\CompetitorsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_id = 56; // int | Only competitors tracked from this Instagram account `id`.

try {
    $result = $apiInstance->listCompetitors($workspace_uuid, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling CompetitorsApi->listCompetitors: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_id** | **int**| Only competitors tracked from this Instagram account &#x60;id&#x60;. | [optional] |

### Return type

[**\PostBoostClient\Model\ListCompetitors200Response**](../Model/ListCompetitors200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
