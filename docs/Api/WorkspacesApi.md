# PostBoostClient\WorkspacesApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addUserToWorkspace()**](WorkspacesApi.md#addUserToWorkspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace |
| [**createApiKey()**](WorkspacesApi.md#createApiKey) | **POST** /{workspaceUuid}/api-keys | Create a scoped API key |
| [**createResellerClient()**](WorkspacesApi.md#createResellerClient) | **POST** /{workspaceUuid}/clients | Create a client workspace |
| [**createWorkspace()**](WorkspacesApi.md#createWorkspace) | **POST** /panel/workspaces | Create workspace |
| [**deleteApiKey()**](WorkspacesApi.md#deleteApiKey) | **DELETE** /{workspaceUuid}/api-keys/{apiKeyId} | Revoke a scoped API key |
| [**deleteWorkspace()**](WorkspacesApi.md#deleteWorkspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace |
| [**deleteWorkspacesBulk()**](WorkspacesApi.md#deleteWorkspacesBulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk) |
| [**getWorkspace()**](WorkspacesApi.md#getWorkspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace |
| [**getWorkspaceAICredits()**](WorkspacesApi.md#getWorkspaceAICredits) | **GET** /panel/workspaces/{workspaceUuid}/ai-credits | Get workspace AI credits |
| [**getXUsage()**](WorkspacesApi.md#getXUsage) | **GET** /{workspaceUuid}/usage/x | X (Twitter) usage |
| [**listApiKeys()**](WorkspacesApi.md#listApiKeys) | **GET** /{workspaceUuid}/api-keys | List scoped API keys |
| [**listMyWorkspaces()**](WorkspacesApi.md#listMyWorkspaces) | **GET** /workspaces | List my workspaces |
| [**listResellerClients()**](WorkspacesApi.md#listResellerClients) | **GET** /{workspaceUuid}/clients | List client workspaces |
| [**listWorkspaces()**](WorkspacesApi.md#listWorkspaces) | **GET** /panel/workspaces | List workspaces |
| [**removeUserFromWorkspace()**](WorkspacesApi.md#removeUserFromWorkspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace |
| [**updateWorkspace()**](WorkspacesApi.md#updateWorkspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace |
| [**updateWorkspaceUser()**](WorkspacesApi.md#updateWorkspaceUser) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace |


## `addUserToWorkspace()`

```php
addUserToWorkspace($workspace_uuid, $workspace_user_input): object
```

Add user to workspace

Adds an existing user to the workspace with a specified role. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$workspace_user_input = new \PostBoostClient\Model\WorkspaceUserInput(); // \PostBoostClient\Model\WorkspaceUserInput

try {
    $result = $apiInstance->addUserToWorkspace($workspace_uuid, $workspace_user_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->addUserToWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **workspace_user_input** | [**\PostBoostClient\Model\WorkspaceUserInput**](../Model/WorkspaceUserInput.md)|  | |

### Return type

**object**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createApiKey()`

```php
createApiKey($workspace_uuid, $api_key_input): \PostBoostClient\Model\CreateApiKey201Response
```

Create a scoped API key

Creates a least-privilege API key for the calling user, bound to this workspace. Pick the abilities it gets and, optionally, the accounts it may act on. The plain key is in `data.token` of this response only; store it safely.  | Ability | Allows | |---|---| | `read` | Every `GET`, plus the `posts/validate` dry run | | `write` | Creating and changing drafts, media, tags, mentions, the brand voice | | `publish` | Scheduling, queueing, publishing now, approving and retrying posts, and editing a post that is already scheduled | | `ai` | The `/ai/_*` endpoints, running agents and turning on agent AI review (they also need AI credits) | | `webhooks` | Webhook subscription endpoints |  A scoped key is refused on other workspaces, on the admin panel, on API key management and on the app's built-in MCP endpoint (use `/mcp/postboost`). With `account_ids`, it may only name those accounts (in the URL, `accounts`, `account_ids` or post versions), cannot touch posts on other accounts, and `GET accounts` / `GET posts` only list matching items (pagination counts are computed before that filter). Workspace admins only, called with an unscoped key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$api_key_input = {"name":"Reporting agent","abilities":["read"],"account_ids":[12,14],"expires_at":"2027-01-31"}; // \PostBoostClient\Model\ApiKeyInput

try {
    $result = $apiInstance->createApiKey($workspace_uuid, $api_key_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->createApiKey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **api_key_input** | [**\PostBoostClient\Model\ApiKeyInput**](../Model/ApiKeyInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateApiKey201Response**](../Model/CreateApiKey201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createResellerClient()`

```php
createResellerClient($workspace_uuid, $reseller_client_input): \PostBoostClient\Model\CreateResellerClient201Response
```

Create a client workspace

Creates a client workspace on the Reseller client plan, with the caller as its owner and admin, and links it to this workspace. Fails with `422` and `code: client_limit_reached` once the plan's client limit is used (archived clients do not count). Archive clients on the Client workspaces page. Workspace admins with an unscoped key only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$reseller_client_input = {"name":"Acme Bakery"}; // \PostBoostClient\Model\ResellerClientInput

try {
    $result = $apiInstance->createResellerClient($workspace_uuid, $reseller_client_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->createResellerClient: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **reseller_client_input** | [**\PostBoostClient\Model\ResellerClientInput**](../Model/ResellerClientInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateResellerClient201Response**](../Model/CreateResellerClient201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createWorkspace()`

```php
createWorkspace($workspace_input): \PostBoostClient\Model\Workspace
```

Create workspace

Create a new workspace. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_input = new \PostBoostClient\Model\WorkspaceInput(); // \PostBoostClient\Model\WorkspaceInput

try {
    $result = $apiInstance->createWorkspace($workspace_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->createWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_input** | [**\PostBoostClient\Model\WorkspaceInput**](../Model/WorkspaceInput.md)|  | |

### Return type

[**\PostBoostClient\Model\Workspace**](../Model/Workspace.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteApiKey()`

```php
deleteApiKey($workspace_uuid, $api_key_id): object
```

Revoke a scoped API key

Revokes a scoped key bound to this workspace. It stops working at once. Workspace admins only, called with an unscoped key.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$api_key_id = 56; // int | The key's `id` from `GET api-keys`.

try {
    $result = $apiInstance->deleteApiKey($workspace_uuid, $api_key_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->deleteApiKey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **api_key_id** | **int**| The key&#39;s &#x60;id&#x60; from &#x60;GET api-keys&#x60;. | |

### Return type

**object**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteWorkspace()`

```php
deleteWorkspace($workspace_uuid): object
```

Delete workspace

Permanently deletes a single workspace and all its associated data. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->deleteWorkspace($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->deleteWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

**object**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteWorkspacesBulk()`

```php
deleteWorkspacesBulk($delete_workspaces_bulk_request): object
```

Delete workspaces (bulk)

Permanently deletes one or more workspaces and all their associated data. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$delete_workspaces_bulk_request = new \PostBoostClient\Model\DeleteWorkspacesBulkRequest(); // \PostBoostClient\Model\DeleteWorkspacesBulkRequest

try {
    $result = $apiInstance->deleteWorkspacesBulk($delete_workspaces_bulk_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->deleteWorkspacesBulk: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **delete_workspaces_bulk_request** | [**\PostBoostClient\Model\DeleteWorkspacesBulkRequest**](../Model/DeleteWorkspacesBulkRequest.md)|  | |

### Return type

**object**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWorkspace()`

```php
getWorkspace($workspace_uuid): \PostBoostClient\Model\Workspace
```

Get workspace

Returns a single workspace by UUID including its subscription status. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->getWorkspace($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->getWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\Workspace**](../Model/Workspace.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getWorkspaceAICredits()`

```php
getWorkspaceAICredits($workspace_uuid): \PostBoostClient\Model\AICredits
```

Get workspace AI credits

Returns whether the workspace can use AI credits, its remaining balance, and whether the balance is low. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->getWorkspaceAICredits($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->getWorkspaceAICredits: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\AICredits**](../Model/AICredits.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getXUsage()`

```php
getXUsage($workspace_uuid): \PostBoostClient\Model\XUsage
```

X (Twitter) usage

The workspace's X posts this calendar month (UTC) against its monthly X allowance. Every thread part is one X post; a part with a link also counts as a link post. Once enforcement is switched on (`enforced: true`), scheduling to X is refused when the allowance is used up (`429`, `code: x_monthly_cap_reached`) and X posts that come due fail with \"Monthly X allowance reached\". Until then usage is tracked only. Other networks are not affected. See the X policy in the developer docs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->getXUsage($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->getXUsage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\XUsage**](../Model/XUsage.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listApiKeys()`

```php
listApiKeys($workspace_uuid): \PostBoostClient\Model\ListApiKeys200Response
```

List scoped API keys

Scoped API keys bound to this workspace, newest first. The secret is never shown again after creation. Workspace admins only, called with an unscoped key (a scoped key gets `403` with `code: insufficient_scope`).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->listApiKeys($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->listApiKeys: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\ListApiKeys200Response**](../Model/ListApiKeys200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listMyWorkspaces()`

```php
listMyWorkspaces(): \PostBoostClient\Model\ListMyWorkspaces200Response
```

List my workspaces

Returns the workspaces the authenticated user belongs to, most recently updated first, with the caller's role in each. Use a returned `uuid` as `workspaceUuid`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->listMyWorkspaces();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->listMyWorkspaces: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\PostBoostClient\Model\ListMyWorkspaces200Response**](../Model/ListMyWorkspaces200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listResellerClients()`

```php
listResellerClients($workspace_uuid): \PostBoostClient\Model\ListResellerClients200Response
```

List client workspaces

Client workspaces this workspace created on the Reseller plan, active first, then archived. `accounts_needing_reconnect` counts accounts whose connection must be renewed. `meta` gives the active clients and the plan's client limit. Workspace admins with an unscoped key only; other workspaces get `403` with `code: not_a_reseller`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->listResellerClients($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->listResellerClients: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\ListResellerClients200Response**](../Model/ListResellerClients200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listWorkspaces()`

```php
listWorkspaces($keyword, $subscription_status, $access_status, $page): \PostBoostClient\Model\ListWorkspaces200Response
```

List workspaces

Returns a paginated list of all workspaces. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$keyword = 'keyword_example'; // string
$subscription_status = 'subscription_status_example'; // string
$access_status = 'access_status_example'; // string
$page = 1; // int | Page number (15 items per page).

try {
    $result = $apiInstance->listWorkspaces($keyword, $subscription_status, $access_status, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->listWorkspaces: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **keyword** | **string**|  | [optional] |
| **subscription_status** | **string**|  | [optional] |
| **access_status** | **string**|  | [optional] |
| **page** | **int**| Page number (15 items per page). | [optional] [default to 1] |

### Return type

[**\PostBoostClient\Model\ListWorkspaces200Response**](../Model/ListWorkspaces200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `removeUserFromWorkspace()`

```php
removeUserFromWorkspace($workspace_uuid, $remove_user_from_workspace_request): object
```

Remove user from workspace

Removes a user's access to the workspace. The user account is not deleted. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$remove_user_from_workspace_request = new \PostBoostClient\Model\RemoveUserFromWorkspaceRequest(); // \PostBoostClient\Model\RemoveUserFromWorkspaceRequest

try {
    $result = $apiInstance->removeUserFromWorkspace($workspace_uuid, $remove_user_from_workspace_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->removeUserFromWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **remove_user_from_workspace_request** | [**\PostBoostClient\Model\RemoveUserFromWorkspaceRequest**](../Model/RemoveUserFromWorkspaceRequest.md)|  | |

### Return type

**object**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateWorkspace()`

```php
updateWorkspace($workspace_uuid, $workspace_input): object
```

Update workspace

Updates a workspace's name, owner, or access status. Admin only. `hex_color` is accepted but ignored.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$workspace_input = new \PostBoostClient\Model\WorkspaceInput(); // \PostBoostClient\Model\WorkspaceInput

try {
    $result = $apiInstance->updateWorkspace($workspace_uuid, $workspace_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->updateWorkspace: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **workspace_input** | [**\PostBoostClient\Model\WorkspaceInput**](../Model/WorkspaceInput.md)|  | |

### Return type

**object**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateWorkspaceUser()`

```php
updateWorkspaceUser($workspace_uuid, $workspace_user_input): object
```

Update user role in workspace

Changes a user's role or permissions within the workspace. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WorkspacesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$workspace_user_input = new \PostBoostClient\Model\WorkspaceUserInput(); // \PostBoostClient\Model\WorkspaceUserInput

try {
    $result = $apiInstance->updateWorkspaceUser($workspace_uuid, $workspace_user_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WorkspacesApi->updateWorkspaceUser: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **workspace_user_input** | [**\PostBoostClient\Model\WorkspaceUserInput**](../Model/WorkspaceUserInput.md)|  | |

### Return type

**object**

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
