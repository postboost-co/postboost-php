# PostBoostClient\AccountGroupsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createAccountGroup()**](AccountGroupsApi.md#createAccountGroup) | **POST** /{workspaceUuid}/account-groups | Create an account group |
| [**deleteAccountGroup()**](AccountGroupsApi.md#deleteAccountGroup) | **DELETE** /{workspaceUuid}/account-groups/{accountGroupUuid} | Delete an account group |
| [**getAccountGroup()**](AccountGroupsApi.md#getAccountGroup) | **GET** /{workspaceUuid}/account-groups/{accountGroupUuid} | Get an account group |
| [**listAccountGroups()**](AccountGroupsApi.md#listAccountGroups) | **GET** /{workspaceUuid}/account-groups | List account groups |
| [**updateAccountGroup()**](AccountGroupsApi.md#updateAccountGroup) | **PUT** /{workspaceUuid}/account-groups/{accountGroupUuid} | Update an account group |


## `createAccountGroup()`

```php
createAccountGroup($workspace_uuid, $account_group_input): \PostBoostClient\Model\CreateAccountGroup201Response
```

Create an account group

Creates a named set of accounts of this workspace. Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_group_input = new \PostBoostClient\Model\AccountGroupInput(); // \PostBoostClient\Model\AccountGroupInput

try {
    $result = $apiInstance->createAccountGroup($workspace_uuid, $account_group_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountGroupsApi->createAccountGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_group_input** | [**\PostBoostClient\Model\AccountGroupInput**](../Model/AccountGroupInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateAccountGroup201Response**](../Model/CreateAccountGroup201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAccountGroup()`

```php
deleteAccountGroup($workspace_uuid, $account_group_uuid)
```

Delete an account group

Deletes the group, not its accounts. Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_group_uuid = 'account_group_uuid_example'; // string | The account group `uuid`.

try {
    $apiInstance->deleteAccountGroup($workspace_uuid, $account_group_uuid);
} catch (Exception $e) {
    echo 'Exception when calling AccountGroupsApi->deleteAccountGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_group_uuid** | **string**| The account group &#x60;uuid&#x60;. | |

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

## `getAccountGroup()`

```php
getAccountGroup($workspace_uuid, $account_group_uuid): \PostBoostClient\Model\CreateAccountGroup201Response
```

Get an account group

One account group.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_group_uuid = 'account_group_uuid_example'; // string | The account group `uuid`.

try {
    $result = $apiInstance->getAccountGroup($workspace_uuid, $account_group_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountGroupsApi->getAccountGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_group_uuid** | **string**| The account group &#x60;uuid&#x60;. | |

### Return type

[**\PostBoostClient\Model\CreateAccountGroup201Response**](../Model/CreateAccountGroup201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAccountGroups()`

```php
listAccountGroups($workspace_uuid, $page, $per_page): \PostBoostClient\Model\ListAccountGroups200Response
```

List account groups

Named sets of accounts, sorted by name, with their account ids. Pass `account_ids` as `accounts` when you create a post to publish to the whole group. Paginated with `page` and `per_page` (default 100). A key limited to some accounts only sees groups whose accounts are all among its accounts, and `meta.total` counts only those.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$page = 1; // int | Page number (1-based).
$per_page = 100; // int | Items per page, 1-100.

try {
    $result = $apiInstance->listAccountGroups($workspace_uuid, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountGroupsApi->listAccountGroups: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **page** | **int**| Page number (1-based). | [optional] [default to 1] |
| **per_page** | **int**| Items per page, 1-100. | [optional] [default to 100] |

### Return type

[**\PostBoostClient\Model\ListAccountGroups200Response**](../Model/ListAccountGroups200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateAccountGroup()`

```php
updateAccountGroup($workspace_uuid, $account_group_uuid, $account_group_input): \PostBoostClient\Model\CreateAccountGroup201Response
```

Update an account group

Replaces the name and the accounts of the group (accounts you leave out are removed). Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountGroupsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_group_uuid = 'account_group_uuid_example'; // string | The account group `uuid`.
$account_group_input = new \PostBoostClient\Model\AccountGroupInput(); // \PostBoostClient\Model\AccountGroupInput

try {
    $result = $apiInstance->updateAccountGroup($workspace_uuid, $account_group_uuid, $account_group_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountGroupsApi->updateAccountGroup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_group_uuid** | **string**| The account group &#x60;uuid&#x60;. | |
| **account_group_input** | [**\PostBoostClient\Model\AccountGroupInput**](../Model/AccountGroupInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateAccountGroup201Response**](../Model/CreateAccountGroup201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
