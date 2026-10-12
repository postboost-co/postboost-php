# PostBoostClient\AnalyticsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createReportExport()**](AnalyticsApi.md#createReportExport) | **POST** /{workspaceUuid}/reports/exports | Create a report export |
| [**downloadReportExport()**](AnalyticsApi.md#downloadReportExport) | **GET** /{workspaceUuid}/reports/exports/{exportUuid}/download | Download a report file |
| [**getAccountAnalytics()**](AnalyticsApi.md#getAccountAnalytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics |
| [**getAnalyticsSummary()**](AnalyticsApi.md#getAnalyticsSummary) | **GET** /{workspaceUuid}/analytics | Get analytics summary |
| [**getBestPostingTimes()**](AnalyticsApi.md#getBestPostingTimes) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times |
| [**getPostAnalytics_0()**](AnalyticsApi.md#getPostAnalytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics |
| [**getPostingTimes()**](AnalyticsApi.md#getPostingTimes) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap |
| [**getReportBranding()**](AnalyticsApi.md#getReportBranding) | **GET** /{workspaceUuid}/report-branding | Get the report branding |
| [**getReportExport()**](AnalyticsApi.md#getReportExport) | **GET** /{workspaceUuid}/reports/exports/{exportUuid} | Get a report export |
| [**listReportExports()**](AnalyticsApi.md#listReportExports) | **GET** /{workspaceUuid}/reports/exports | List report exports |
| [**updateReportBranding()**](AnalyticsApi.md#updateReportBranding) | **PUT** /{workspaceUuid}/report-branding | Update the report branding |
| [**uploadReportBrandingLogo()**](AnalyticsApi.md#uploadReportBrandingLogo) | **POST** /{workspaceUuid}/report-branding/logo | Upload the report logo |


## `createReportExport()`

```php
createReportExport($workspace_uuid, $report_export_input): \PostBoostClient\Model\CreateReportExport201Response
```

Create a report export

Generates a report for a period (default `last_month`) or a custom `date_from`/`date_to` range: a branded PDF (summary, accounts, top 10 posts; the header uses the report branding) or a CSV with one row per published post and account (`dataset: posts`, default) or per account (`dataset: accounts`). CSV files are UTF-8 with a byte order mark. At most 500 posts per report. The file is ready when the call returns; fetch it from `download_url` with the same token. Admins and members only; 20 per minute.

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
$report_export_input = {"format":"pdf","period":"last_month"}; // \PostBoostClient\Model\ReportExportInput

try {
    $result = $apiInstance->createReportExport($workspace_uuid, $report_export_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->createReportExport: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **report_export_input** | [**\PostBoostClient\Model\ReportExportInput**](../Model/ReportExportInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateReportExport201Response**](../Model/CreateReportExport201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `downloadReportExport()`

```php
downloadReportExport($workspace_uuid, $export_uuid): \SplFileObject
```

Download a report file

The PDF or CSV file. `410` once it expired (7 days) or if the export failed.

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
$export_uuid = 'export_uuid_example'; // string | UUID of the report export.

try {
    $result = $apiInstance->downloadReportExport($workspace_uuid, $export_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->downloadReportExport: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **export_uuid** | **string**| UUID of the report export. | |

### Return type

**\SplFileObject**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/pdf`, `text/csv`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

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

## `getReportBranding()`

```php
getReportBranding($workspace_uuid): \PostBoostClient\Model\GetReportBranding200Response
```

Get the report branding

The white-label header of the workspace's PDF reports. Unset fields are `null`; the workspace name is used then.

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

try {
    $result = $apiInstance->getReportBranding($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->getReportBranding: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\GetReportBranding200Response**](../Model/GetReportBranding200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getReportExport()`

```php
getReportExport($workspace_uuid, $export_uuid): \PostBoostClient\Model\CreateReportExport201Response
```

Get a report export

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
$export_uuid = 'export_uuid_example'; // string | UUID of the report export.

try {
    $result = $apiInstance->getReportExport($workspace_uuid, $export_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->getReportExport: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **export_uuid** | **string**| UUID of the report export. | |

### Return type

[**\PostBoostClient\Model\CreateReportExport201Response**](../Model/CreateReportExport201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listReportExports()`

```php
listReportExports($workspace_uuid): \PostBoostClient\Model\ListReportExports200Response
```

List report exports

The workspace's latest 50 report exports, newest first. Files can be downloaded for 7 days.

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

try {
    $result = $apiInstance->listReportExports($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->listReportExports: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\ListReportExports200Response**](../Model/ListReportExports200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateReportBranding()`

```php
updateReportBranding($workspace_uuid, $report_branding_input): \PostBoostClient\Model\GetReportBranding200Response
```

Update the report branding

Name, colour and footer of PDF reports. Fields you leave out keep their value. Upload the logo with `uploadReportBrandingLogo`. Admins and members only.

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
$report_branding_input = {"display_name":"Brightside Agency","primary_color":"#FF6600","footer_text":"Prepared by Brightside Agency","show_powered_by":false}; // \PostBoostClient\Model\ReportBrandingInput

try {
    $result = $apiInstance->updateReportBranding($workspace_uuid, $report_branding_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->updateReportBranding: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **report_branding_input** | [**\PostBoostClient\Model\ReportBrandingInput**](../Model/ReportBrandingInput.md)|  | |

### Return type

[**\PostBoostClient\Model\GetReportBranding200Response**](../Model/GetReportBranding200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `uploadReportBrandingLogo()`

```php
uploadReportBrandingLogo($workspace_uuid, $logo): \PostBoostClient\Model\GetReportBranding200Response
```

Upload the report logo

PNG or JPEG, up to 1 MB (SVG is not accepted). Replaces the current logo. Admins and members only.

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
$logo = "/path/to/file.txt"; // \SplFileObject

try {
    $result = $apiInstance->uploadReportBrandingLogo($workspace_uuid, $logo);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AnalyticsApi->uploadReportBrandingLogo: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **logo** | **\SplFileObject****\SplFileObject**|  | |

### Return type

[**\PostBoostClient\Model\GetReportBranding200Response**](../Model/GetReportBranding200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
