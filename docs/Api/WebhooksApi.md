# PostBoostClient\WebhooksApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createWebhookSubscription()**](WebhooksApi.md#createWebhookSubscription) | **POST** /{workspaceUuid}/webhooks/subscriptions | Subscribe a webhook |
| [**deleteWebhookSubscription()**](WebhooksApi.md#deleteWebhookSubscription) | **DELETE** /{workspaceUuid}/webhooks/subscriptions/{subscriptionUuid} | Unsubscribe a webhook |
| [**listWebhookSubscriptions()**](WebhooksApi.md#listWebhookSubscriptions) | **GET** /{workspaceUuid}/webhooks/subscriptions | List webhook subscriptions |


## `createWebhookSubscription()`

```php
createWebhookSubscription($workspace_uuid, $webhook_subscription_input): \PostBoostClient\Model\CreateWebhookSubscription201Response
```

Subscribe a webhook

Registers a callback URL for the given events, the way n8n, Zapier and Make instant triggers do. Deliveries are `POST` requests with a JSON body (see [Webhooks](/webhooks) for the payload), signed with the returned `secret` in `X-Signature` (HMAC-SHA256 of the raw body, hex encoded) and attempted up to 3 times. Only public `https://` URLs are accepted. The `secret` is in this response only. Workspace admins only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$webhook_subscription_input = {"callback_url":"https://n8n.example.com/webhook/7d1c0c2e/postboost","events":["post.published","post.publishing_failed"],"source":"n8n"}; // \PostBoostClient\Model\WebhookSubscriptionInput

try {
    $result = $apiInstance->createWebhookSubscription($workspace_uuid, $webhook_subscription_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->createWebhookSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **webhook_subscription_input** | [**\PostBoostClient\Model\WebhookSubscriptionInput**](../Model/WebhookSubscriptionInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateWebhookSubscription201Response**](../Model/CreateWebhookSubscription201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteWebhookSubscription()`

```php
deleteWebhookSubscription($workspace_uuid, $subscription_uuid): object
```

Unsubscribe a webhook

Deletes the webhook and stops its deliveries. Workspace admins only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$subscription_uuid = 'subscription_uuid_example'; // string | UUID of the webhook subscription.

try {
    $result = $apiInstance->deleteWebhookSubscription($workspace_uuid, $subscription_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->deleteWebhookSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **subscription_uuid** | **string**| UUID of the webhook subscription. | |

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

## `listWebhookSubscriptions()`

```php
listWebhookSubscriptions($workspace_uuid): \PostBoostClient\Model\ListWebhookSubscriptions200Response
```

List webhook subscriptions

The workspace's webhooks, newest first: subscriptions created through this API and the ones added in **Settings → Webhooks**. Secrets are never returned here. Workspace admins only; needs the `webhooks` plan capability and, for scoped keys, the `webhooks` ability.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\WebhooksApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->listWebhookSubscriptions($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WebhooksApi->listWebhookSubscriptions: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\ListWebhookSubscriptions200Response**](../Model/ListWebhookSubscriptions200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
