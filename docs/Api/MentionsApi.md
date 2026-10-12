# PostBoostClient\MentionsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createMention()**](MentionsApi.md#createMention) | **POST** /{workspaceUuid}/mentions | Create mention |
| [**deleteMention()**](MentionsApi.md#deleteMention) | **DELETE** /{workspaceUuid}/mentions/{mentionId} | Delete mention |
| [**getMention()**](MentionsApi.md#getMention) | **GET** /{workspaceUuid}/mentions/{mentionId} | Get mention |
| [**listMentions()**](MentionsApi.md#listMentions) | **GET** /{workspaceUuid}/mentions | List mentions |
| [**updateMention()**](MentionsApi.md#updateMention) | **PUT** /{workspaceUuid}/mentions/{mentionId} | Update mention |


## `createMention()`

```php
createMention($workspace_uuid, $mention_input, $idempotency_key): \PostBoostClient\Model\CreateMention201Response
```

Create mention

Adds a person or page to the mention book. When one of the submitted identities already belongs to a stored mention, that mention is reused and the identities are added to it (status `200` instead of `201`).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MentionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$mention_input = new \PostBoostClient\Model\MentionInput(); // \PostBoostClient\Model\MentionInput
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.

try {
    $result = $apiInstance->createMention($workspace_uuid, $mention_input, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MentionsApi->createMention: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **mention_input** | [**\PostBoostClient\Model\MentionInput**](../Model/MentionInput.md)|  | |
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |

### Return type

[**\PostBoostClient\Model\CreateMention201Response**](../Model/CreateMention201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteMention()`

```php
deleteMention($workspace_uuid, $mention_id): object
```

Delete mention

Removes a mention from the mention book. `success` is false when nothing was deleted.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MentionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$mention_id = 'mention_id_example'; // string | The mention's `id` (a UUID).

try {
    $result = $apiInstance->deleteMention($workspace_uuid, $mention_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MentionsApi->deleteMention: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **mention_id** | **string**| The mention&#39;s &#x60;id&#x60; (a UUID). | |

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

## `getMention()`

```php
getMention($workspace_uuid, $mention_id): \PostBoostClient\Model\CreateMention201Response
```

Get mention

Returns a single mention with its identities.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MentionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$mention_id = 'mention_id_example'; // string | The mention's `id` (a UUID).

try {
    $result = $apiInstance->getMention($workspace_uuid, $mention_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MentionsApi->getMention: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **mention_id** | **string**| The mention&#39;s &#x60;id&#x60; (a UUID). | |

### Return type

[**\PostBoostClient\Model\CreateMention201Response**](../Model/CreateMention201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listMentions()`

```php
listMentions($workspace_uuid, $q, $per_page, $page): \PostBoostClient\Model\ListMentions200Response
```

List mentions

Returns a paginated list of the workspace's mention book, ranked, with each entry's network identities.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MentionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$q = 'q_example'; // string | Search keyword.
$per_page = 25; // int
$page = 1; // int

try {
    $result = $apiInstance->listMentions($workspace_uuid, $q, $per_page, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MentionsApi->listMentions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **q** | **string**| Search keyword. | [optional] |
| **per_page** | **int**|  | [optional] [default to 25] |
| **page** | **int**|  | [optional] [default to 1] |

### Return type

[**\PostBoostClient\Model\ListMentions200Response**](../Model/ListMentions200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateMention()`

```php
updateMention($workspace_uuid, $mention_id, $mention_input): \PostBoostClient\Model\CreateMention201Response
```

Update mention

Replaces the mention's name, avatar and identities. Identities for providers not in the payload are removed. An identity already held by another mention returns `422`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MentionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$mention_id = 'mention_id_example'; // string | The mention's `id` (a UUID).
$mention_input = new \PostBoostClient\Model\MentionInput(); // \PostBoostClient\Model\MentionInput

try {
    $result = $apiInstance->updateMention($workspace_uuid, $mention_id, $mention_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MentionsApi->updateMention: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **mention_id** | **string**| The mention&#39;s &#x60;id&#x60; (a UUID). | |
| **mention_input** | [**\PostBoostClient\Model\MentionInput**](../Model/MentionInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateMention201Response**](../Model/CreateMention201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
