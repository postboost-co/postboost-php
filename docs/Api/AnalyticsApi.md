# PostBoostClient\AnalyticsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**getAccountAnalytics()**](AnalyticsApi.md#getAccountAnalytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics |
| [**getAnalyticsSummary()**](AnalyticsApi.md#getAnalyticsSummary) | **GET** /{workspaceUuid}/analytics | Get analytics summary |
| [**getBestPostingTimes()**](AnalyticsApi.md#getBestPostingTimes) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times |
| [**getPostAnalytics_0()**](AnalyticsApi.md#getPostAnalytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics |
| [**getPostingTimes()**](AnalyticsApi.md#getPostingTimes) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap |


## `getAccountAnalytics()`

```php
getAccountAnalytics($workspace_uuid, $account_uuid, $period, $date_from, $date_to, $type, $page, $per_page, $sort_by, $sort_dir): \PostBoostClient\Model\AccountAnalytics
```

Get account analytics

Analytics for one account. `type` selects one of the tabs the account supports (listed in `tabs` of the response); returns `422` when the account does not support analytics.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AnalyticsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_uuid = 'account_uuid_example'; // string | UUID of the social media account.
$period = 'this_month'; // string | Preset reporting period. Ignored when `date_from` and `date_to` are given.
$date_from = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Start of a custom range (Y-m-d). Required with `date_to`; the range may span at most 366 days.
$date_to = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | End of a custom range (Y-m-d). Required with `date_from`; must not be before it.
$type = 'type_example'; // string | Analytics tab. Defaults to the account's default tab.
$page = 1; // int | Page for list-style tabs (for example per-post metrics).
$per_page = 56; // int
$sort_by = 'sort_by_example'; // string
$sort_dir = 'desc'; // string

try {
    $result = $apiInstance->getAccountAnalytics($workspace_uuid, $account_uuid, $period, $date_from, $date_to, $type, $page, $per_page, $sort_by, $sort_dir);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->getAccountAnalytics: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_uuid** | **string**| UUID of the social media account. | |
| **period** | **string**| Preset reporting period. Ignored when &#x60;date_from&#x60; and &#x60;date_to&#x60; are given. | [optional] [default to &#39;this_month&#39;] |
| **date_from** | **\DateTime**| Start of a custom range (Y-m-d). Required with &#x60;date_to&#x60;; the range may span at most 366 days. | [optional] |
| **date_to** | **\DateTime**| End of a custom range (Y-m-d). Required with &#x60;date_from&#x60;; must not be before it. | [optional] |
| **type** | **string**| Analytics tab. Defaults to the account&#39;s default tab. | [optional] |
| **page** | **int**| Page for list-style tabs (for example per-post metrics). | [optional] [default to 1] |
| **per_page** | **int**|  | [optional] |
| **sort_by** | **string**|  | [optional] |
| **sort_dir** | **string**|  | [optional] [default to &#39;desc&#39;] |

### Return type

[**\PostBoostClient\Model\AccountAnalytics**](../Model/AccountAnalytics.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAnalyticsSummary()`

```php
getAnalyticsSummary($workspace_uuid, $period, $date_from, $date_to): \PostBoostClient\Model\AnalyticsSummary
```

Get analytics summary

Cross-platform summary (followers, growth, posts, leaderboard, posting streak) over every account that supports analytics, for a preset period or a custom date range.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AnalyticsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$period = 'this_month'; // string | Preset reporting period. Ignored when `date_from` and `date_to` are given.
$date_from = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Start of a custom range (Y-m-d). Required with `date_to`; the range may span at most 366 days.
$date_to = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | End of a custom range (Y-m-d). Required with `date_from`; must not be before it.

try {
    $result = $apiInstance->getAnalyticsSummary($workspace_uuid, $period, $date_from, $date_to);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->getAnalyticsSummary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **period** | **string**| Preset reporting period. Ignored when &#x60;date_from&#x60; and &#x60;date_to&#x60; are given. | [optional] [default to &#39;this_month&#39;] |
| **date_from** | **\DateTime**| Start of a custom range (Y-m-d). Required with &#x60;date_to&#x60;; the range may span at most 366 days. | [optional] |
| **date_to** | **\DateTime**| End of a custom range (Y-m-d). Required with &#x60;date_from&#x60;; must not be before it. | [optional] |

### Return type

[**\PostBoostClient\Model\AnalyticsSummary**](../Model/AnalyticsSummary.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBestPostingTimes()`

```php
getBestPostingTimes($workspace_uuid, $accounts, $from, $timezone): \PostBoostClient\Model\BestPostingTimes
```

Get best posting times

The next recommended date and time per account, on or after `from` (never in the past), within the next 14 days.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AnalyticsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$accounts = array('accounts_example'); // string[] | Account UUIDs. Defaults to every account in the workspace.
$from = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Earliest date to recommend (Y-m-d). Defaults to now.
$timezone = 'timezone_example'; // string | Timezone for `from` and the returned times. Defaults to the workspace timezone.

try {
    $result = $apiInstance->getBestPostingTimes($workspace_uuid, $accounts, $from, $timezone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->getBestPostingTimes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **accounts** | [**string[]**](../Model/string.md)| Account UUIDs. Defaults to every account in the workspace. | [optional] |
| **from** | **\DateTime**| Earliest date to recommend (Y-m-d). Defaults to now. | [optional] |
| **timezone** | **string**| Timezone for &#x60;from&#x60; and the returned times. Defaults to the workspace timezone. | [optional] |

### Return type

[**\PostBoostClient\Model\BestPostingTimes**](../Model/BestPostingTimes.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPostAnalytics_0()`

```php
getPostAnalytics_0($workspace_uuid, $post_uuid): \PostBoostClient\Model\PostAnalytics
```

Get post analytics

Engagement metrics for a published post across its accounts (also works for trashed posts), with totals, trends and the best-performing account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AnalyticsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$post_uuid = 'post_uuid_example'; // string | UUID of the post.

try {
    $result = $apiInstance->getPostAnalytics_0($workspace_uuid, $post_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->getPostAnalytics_0: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |

### Return type

[**\PostBoostClient\Model\PostAnalytics**](../Model/PostAnalytics.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPostingTimes()`

```php
getPostingTimes($workspace_uuid, $accounts, $timezone): \PostBoostClient\Model\PostingTimes
```

Get posting times heatmap

Engagement scores per weekday and hour, merged across the given accounts (all accounts when none is given), in the requested timezone. Also returns up to three recommended slots.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AnalyticsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$accounts = array('accounts_example'); // string[] | Account UUIDs. Defaults to every account in the workspace.
$timezone = Europe/Istanbul; // string | Timezone the grid is expressed in. Defaults to the workspace timezone.

try {
    $result = $apiInstance->getPostingTimes($workspace_uuid, $accounts, $timezone);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->getPostingTimes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **accounts** | [**string[]**](../Model/string.md)| Account UUIDs. Defaults to every account in the workspace. | [optional] |
| **timezone** | **string**| Timezone the grid is expressed in. Defaults to the workspace timezone. | [optional] |

### Return type

[**\PostBoostClient\Model\PostingTimes**](../Model/PostingTimes.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
