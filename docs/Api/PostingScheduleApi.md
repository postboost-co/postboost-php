# PostBoostClient\PostingScheduleApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getPostingSchedule()**](PostingScheduleApi.md#getPostingSchedule) | **GET** /{workspaceUuid}/posting-schedule | Get the posting schedule |
| [**getRecommendedPostingTimes()**](PostingScheduleApi.md#getRecommendedPostingTimes) | **GET** /{workspaceUuid}/posting-schedule/recommended | Get recommended posting times |
| [**listQueueSlots()**](PostingScheduleApi.md#listQueueSlots) | **GET** /{workspaceUuid}/queue/slots | List upcoming queue slots |
| [**resetAccountPostingSchedule()**](PostingScheduleApi.md#resetAccountPostingSchedule) | **DELETE** /{workspaceUuid}/posting-schedule/{accountId} | Reset an account schedule |
| [**updatePostingSchedule()**](PostingScheduleApi.md#updatePostingSchedule) | **PUT** /{workspaceUuid}/posting-schedule | Set the posting schedule |


## `getPostingSchedule()`

```php
getPostingSchedule($workspace_uuid, $account_id): \PostBoostClient\Model\GetPostingSchedule200Response
```

Get the posting schedule

The queue's posting times: per weekday, a list of clock times in the schedule's timezone. `account_id=0` is the workspace schedule. An account without its own schedule follows the workspace one (`inherited: true`, `source_account_id: 0`). Posts added to the queue take the next free time.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostingScheduleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_id = 0; // int | `0` (default) for the workspace schedule, or an account `id`.

try {
    $result = $apiInstance->getPostingSchedule($workspace_uuid, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostingScheduleApi->getPostingSchedule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_id** | **int**| &#x60;0&#x60; (default) for the workspace schedule, or an account &#x60;id&#x60;. | [optional] [default to 0] |

### Return type

[**\PostBoostClient\Model\GetPostingSchedule200Response**](../Model/GetPostingSchedule200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRecommendedPostingTimes()`

```php
getRecommendedPostingTimes($workspace_uuid, $account_id, $slots_per_day): \PostBoostClient\Model\RecommendedPostingTimes
```

Get recommended posting times

Suggested posting times from past engagement, in the schedule's timezone. `has_data` is false until there is enough analytics history.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostingScheduleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_id = 0; // int | `0` (default) for the workspace schedule, or an account `id`.
$slots_per_day = 56; // int | Times to suggest per day (1 to 6).

try {
    $result = $apiInstance->getRecommendedPostingTimes($workspace_uuid, $account_id, $slots_per_day);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostingScheduleApi->getRecommendedPostingTimes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_id** | **int**| &#x60;0&#x60; (default) for the workspace schedule, or an account &#x60;id&#x60;. | [optional] [default to 0] |
| **slots_per_day** | **int**| Times to suggest per day (1 to 6). | [optional] |

### Return type

[**\PostBoostClient\Model\RecommendedPostingTimes**](../Model/RecommendedPostingTimes.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listQueueSlots()`

```php
listQueueSlots($workspace_uuid, $account_id, $after): \PostBoostClient\Model\QueueSlots
```

List upcoming queue slots

The queue read forward: upcoming posting times, filled by scheduled posts where they land on one. Page with `after` set to the previous `next_cursor`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostingScheduleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_id = 0; // int | `0` (default) for the workspace schedule, or an account `id`.
$after = 'after_example'; // string | Start after this time (`Y-m-d H:i:s`, UTC), from `next_cursor`.

try {
    $result = $apiInstance->listQueueSlots($workspace_uuid, $account_id, $after);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostingScheduleApi->listQueueSlots: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_id** | **int**| &#x60;0&#x60; (default) for the workspace schedule, or an account &#x60;id&#x60;. | [optional] [default to 0] |
| **after** | **string**| Start after this time (&#x60;Y-m-d H:i:s&#x60;, UTC), from &#x60;next_cursor&#x60;. | [optional] |

### Return type

[**\PostBoostClient\Model\QueueSlots**](../Model/QueueSlots.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `resetAccountPostingSchedule()`

```php
resetAccountPostingSchedule($workspace_uuid, $account_id): \PostBoostClient\Model\GetPostingSchedule200Response
```

Reset an account schedule

Removes the account's own schedule so it follows the workspace schedule again. Workspace admins only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostingScheduleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_id = 56; // int | The account `id`.

try {
    $result = $apiInstance->resetAccountPostingSchedule($workspace_uuid, $account_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostingScheduleApi->resetAccountPostingSchedule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_id** | **int**| The account &#x60;id&#x60;. | |

### Return type

[**\PostBoostClient\Model\GetPostingSchedule200Response**](../Model/GetPostingSchedule200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updatePostingSchedule()`

```php
updatePostingSchedule($workspace_uuid, $posting_schedule_input): \PostBoostClient\Model\GetPostingSchedule200Response
```

Set the posting schedule

Sets the workspace schedule (`account_id: 0`) or gives one account its own schedule. Send all seven weekdays (ids 1 to 6 for Monday to Saturday, 0 for Sunday). Workspace admins only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostingScheduleApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$posting_schedule_input = new \PostBoostClient\Model\PostingScheduleInput(); // \PostBoostClient\Model\PostingScheduleInput

try {
    $result = $apiInstance->updatePostingSchedule($workspace_uuid, $posting_schedule_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostingScheduleApi->updatePostingSchedule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **posting_schedule_input** | [**\PostBoostClient\Model\PostingScheduleInput**](../Model/PostingScheduleInput.md)|  | |

### Return type

[**\PostBoostClient\Model\GetPostingSchedule200Response**](../Model/GetPostingSchedule200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
