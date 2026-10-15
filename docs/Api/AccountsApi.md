# PostBoostClient\AccountsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**connectChannel()**](AccountsApi.md#connectChannel) | **POST** /{workspaceUuid}/accounts/connect/{provider} | Connect a Telegram, Discord or Slack channel |
| [**createConnectLink()**](AccountsApi.md#createConnectLink) | **POST** /{workspaceUuid}/accounts/connect-links | Create a connect link |
| [**createReconnectLink()**](AccountsApi.md#createReconnectLink) | **POST** /{workspaceUuid}/accounts/{accountUuid}/reconnect-links | Create a reconnect link |
| [**getAccount()**](AccountsApi.md#getAccount) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account |
| [**getAccountHealth()**](AccountsApi.md#getAccountHealth) | **GET** /{workspaceUuid}/account-health | Account health |
| [**listAccounts()**](AccountsApi.md#listAccounts) | **GET** /{workspaceUuid}/accounts | List accounts |


## `connectChannel()`

```php
connectChannel($workspace_uuid, $provider, $connect_channel_input): \PostBoostClient\Model\ChannelAccount
```

Connect a Telegram, Discord or Slack channel

Connects a channel that uses a bot token or a webhook URL instead of a login. The credentials are checked against the network first, stored encrypted and never returned. Connecting the same channel again updates it (`200`) instead of adding a second account. Workspace admins only; counts toward the plan's social account limit.  - **telegram**: `bot_token` from @BotFather and `chat` (the channel's `@username`, or its   numeric id such as `-1001234567890` for a private channel). The bot must be an administrator   of the channel allowed to post messages. - **discord**: `webhook_url` from Channel settings → Integrations → Webhooks   (`https://discord.com/api/webhooks/…`). - **slack**: `webhook_url` of an incoming webhook (`https://hooks.slack.com/services/…`) and an   optional display `name`. Slack posts cannot be deleted from PostBoost, and images must be   publicly reachable.  Webhook URLs on any other host are refused (`422`) before any request is made.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$provider = 'provider_example'; // string
$connect_channel_input = new \PostBoostClient\Model\ConnectChannelInput(); // \PostBoostClient\Model\ConnectChannelInput

try {
    $result = $apiInstance->connectChannel($workspace_uuid, $provider, $connect_channel_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->connectChannel: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **provider** | **string**|  | |
| **connect_channel_input** | [**\PostBoostClient\Model\ConnectChannelInput**](../Model/ConnectChannelInput.md)|  | |

### Return type

[**\PostBoostClient\Model\ChannelAccount**](../Model/ChannelAccount.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createConnectLink()`

```php
createConnectLink($workspace_uuid, $create_connect_link_request): \PostBoostClient\Model\ConnectLink
```

Create a connect link

Creates a single-use link (valid 15 minutes) to connect a new account on an OAuth network to this workspace: ask the user to open it in their browser while logged in to PostBoost, wait until they confirm, then call `list-accounts` to get the new account id. The link signs no one in: only the user who created it, while a workspace admin, can use it. Telegram, Discord and Slack need no browser: connect them with `connectChannel`. Mastodon, Pixelfed and Bluesky ask for a server or handle first, so the user connects them in the app. Workspace admins only; at most 10 links per minute.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$create_connect_link_request = new \PostBoostClient\Model\CreateConnectLinkRequest(); // \PostBoostClient\Model\CreateConnectLinkRequest

try {
    $result = $apiInstance->createConnectLink($workspace_uuid, $create_connect_link_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->createConnectLink: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **create_connect_link_request** | [**\PostBoostClient\Model\CreateConnectLinkRequest**](../Model/CreateConnectLinkRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\ConnectLink**](../Model/ConnectLink.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createReconnectLink()`

```php
createReconnectLink($workspace_uuid, $account_uuid): \PostBoostClient\Model\ReconnectLink
```

Create a reconnect link

Creates a single-use link (valid 7 days) that lets someone without a PostBoost login, such as an agency's client, re-authorize this one account on its network. The link only refreshes the connection of this account; signing in as a different profile or page changes nothing. Workspace admins only. Available for Facebook Pages, Instagram, Threads, LinkedIn, TikTok, YouTube and Pinterest. Returns `404` while the feature is not enabled on this instance.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_uuid = 'account_uuid_example'; // string | UUID of the social media account.

try {
    $result = $apiInstance->createReconnectLink($workspace_uuid, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->createReconnectLink: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_uuid** | **string**| UUID of the social media account. | |

### Return type

[**\PostBoostClient\Model\ReconnectLink**](../Model/ReconnectLink.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAccount()`

```php
getAccount($workspace_uuid, $account_uuid): \PostBoostClient\Model\Account
```

Get account

Returns a single social media account.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_uuid = 'account_uuid_example'; // string | UUID of the social media account.

try {
    $result = $apiInstance->getAccount($workspace_uuid, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **account_uuid** | **string**| UUID of the social media account. | |

### Return type

[**\PostBoostClient\Model\Account**](../Model/Account.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAccountHealth()`

```php
getAccountHealth($workspace_uuid): \PostBoostClient\Model\GetAccountHealth200Response
```

Account health

Pre-flight health of every account in the workspace: whether it is authorized and holds an access token, how much of its daily post cap (per UTC day, scheduled, awaiting approval and published posts) is used today, and its connection health: predicted token expiry, latest publish outcome and where to reconnect it. The `account.token_expiring` and `account.disconnected` webhooks report changes as they happen.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->getAccountHealth($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getAccountHealth: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\GetAccountHealth200Response**](../Model/GetAccountHealth200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAccounts()`

```php
listAccounts($workspace_uuid, $keyword, $group, $providers, $unauthorized): \PostBoostClient\Model\ListAccounts200Response
```

List accounts

Returns all social media accounts connected to the workspace, newest first. Optional filters narrow the list.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$keyword = 'keyword_example'; // string | Match the account name or username.
$group = 'group_example'; // string | Only accounts in this account group.
$providers = array('providers_example'); // string[] | Only accounts of these providers (for example `instagram`, `linkedin`).
$unauthorized = True; // bool | When `true`, only accounts that need to be reconnected.

try {
    $result = $apiInstance->listAccounts($workspace_uuid, $keyword, $group, $providers, $unauthorized);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->listAccounts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **keyword** | **string**| Match the account name or username. | [optional] |
| **group** | **string**| Only accounts in this account group. | [optional] |
| **providers** | [**string[]**](../Model/string.md)| Only accounts of these providers (for example &#x60;instagram&#x60;, &#x60;linkedin&#x60;). | [optional] |
| **unauthorized** | **bool**| When &#x60;true&#x60;, only accounts that need to be reconnected. | [optional] |

### Return type

[**\PostBoostClient\Model\ListAccounts200Response**](../Model/ListAccounts200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
