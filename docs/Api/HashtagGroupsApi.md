# PostBoostClient\HashtagGroupsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createHashtagGroup()**](HashtagGroupsApi.md#createHashtagGroup) | **POST** /{workspaceUuid}/hashtag-groups | Create a hashtag group |
| [**deleteHashtagGroup()**](HashtagGroupsApi.md#deleteHashtagGroup) | **DELETE** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Delete a hashtag group |
| [**getHashtagGroup()**](HashtagGroupsApi.md#getHashtagGroup) | **GET** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Get a hashtag group |
| [**listHashtagGroups()**](HashtagGroupsApi.md#listHashtagGroups) | **GET** /{workspaceUuid}/hashtag-groups | List hashtag groups |
| [**updateHashtagGroup()**](HashtagGroupsApi.md#updateHashtagGroup) | **PUT** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Update a hashtag group |


## `createHashtagGroup()`

```php
createHashtagGroup($workspace_uuid, $hashtag_group_input): \PostBoostClient\Model\CreateHashtagGroup201Response
```

Create a hashtag group

Saves a named set of hashtags (up to 3000 characters). Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\HashtagGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$hashtag_group_input = new \PostBoostClient\Model\HashtagGroupInput(); // \PostBoostClient\Model\HashtagGroupInput

try {
    $result = $apiInstance->createHashtagGroup($workspace_uuid, $hashtag_group_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HashtagGroupsApi->createHashtagGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **hashtag_group_input** | [**\PostBoostClient\Model\HashtagGroupInput**](../Model/HashtagGroupInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateHashtagGroup201Response**](../Model/CreateHashtagGroup201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteHashtagGroup()`

```php
deleteHashtagGroup($workspace_uuid, $hashtag_group_id)
```

Delete a hashtag group

Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\HashtagGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$hashtag_group_id = 'hashtag_group_id_example'; // string | The hashtag group `id`.

try {
    $apiInstance->deleteHashtagGroup($workspace_uuid, $hashtag_group_id);
} catch (Exception $e) {
    echo 'Exception when calling HashtagGroupsApi->deleteHashtagGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **hashtag_group_id** | **string**| The hashtag group &#x60;id&#x60;. | |

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

## `getHashtagGroup()`

```php
getHashtagGroup($workspace_uuid, $hashtag_group_id): \PostBoostClient\Model\CreateHashtagGroup201Response
```

Get a hashtag group

One hashtag group.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\HashtagGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$hashtag_group_id = 'hashtag_group_id_example'; // string | The hashtag group `id`.

try {
    $result = $apiInstance->getHashtagGroup($workspace_uuid, $hashtag_group_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HashtagGroupsApi->getHashtagGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **hashtag_group_id** | **string**| The hashtag group &#x60;id&#x60;. | |

### Return type

[**\PostBoostClient\Model\CreateHashtagGroup201Response**](../Model/CreateHashtagGroup201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listHashtagGroups()`

```php
listHashtagGroups($workspace_uuid, $page, $per_page): \PostBoostClient\Model\ListHashtagGroups200Response
```

List hashtag groups

Saved hashtag sets of the workspace, newest first. Paginated with `page` and `per_page` (default 100).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\HashtagGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$page = 1; // int | Page number (1-based).
$per_page = 100; // int | Items per page, 1-100.

try {
    $result = $apiInstance->listHashtagGroups($workspace_uuid, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HashtagGroupsApi->listHashtagGroups: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **page** | **int**| Page number (1-based). | [optional] [default to 1] |
| **per_page** | **int**| Items per page, 1-100. | [optional] [default to 100] |

### Return type

[**\PostBoostClient\Model\ListHashtagGroups200Response**](../Model/ListHashtagGroups200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateHashtagGroup()`

```php
updateHashtagGroup($workspace_uuid, $hashtag_group_id, $hashtag_group_input): \PostBoostClient\Model\CreateHashtagGroup201Response
```

Update a hashtag group

Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\HashtagGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$hashtag_group_id = 'hashtag_group_id_example'; // string | The hashtag group `id`.
$hashtag_group_input = new \PostBoostClient\Model\HashtagGroupInput(); // \PostBoostClient\Model\HashtagGroupInput

try {
    $result = $apiInstance->updateHashtagGroup($workspace_uuid, $hashtag_group_id, $hashtag_group_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling HashtagGroupsApi->updateHashtagGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **hashtag_group_id** | **string**| The hashtag group &#x60;id&#x60;. | |
| **hashtag_group_input** | [**\PostBoostClient\Model\HashtagGroupInput**](../Model/HashtagGroupInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateHashtagGroup201Response**](../Model/CreateHashtagGroup201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
