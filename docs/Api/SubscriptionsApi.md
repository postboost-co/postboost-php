# PostBoostClient\SubscriptionsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addGenericSubscription()**](SubscriptionsApi.md#addGenericSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/generic | Add generic subscription |
| [**cancelSubscription()**](SubscriptionsApi.md#cancelSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/cancel | Cancel subscription |
| [**changeSubscriptionPlan()**](SubscriptionsApi.md#changeSubscriptionPlan) | **PUT** /panel/workspaces/{workspaceUuid}/subscription/change-plan | Change subscription plan |
| [**checkoutSubscription()**](SubscriptionsApi.md#checkoutSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/new | New subscription checkout |
| [**createSubscription()**](SubscriptionsApi.md#createSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription | Create subscription |
| [**deleteSubscription()**](SubscriptionsApi.md#deleteSubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription | Delete subscription |
| [**getSubscription()**](SubscriptionsApi.md#getSubscription) | **GET** /panel/workspaces/{workspaceUuid}/subscription | Get subscription |
| [**removeGenericSubscription()**](SubscriptionsApi.md#removeGenericSubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription/generic | Remove generic subscription |
| [**resumeSubscription()**](SubscriptionsApi.md#resumeSubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/resume | Resume subscription |
| [**updateSubscription()**](SubscriptionsApi.md#updateSubscription) | **PUT** /panel/workspaces/{workspaceUuid}/subscription | Update subscription |


## `addGenericSubscription()`

```php
addGenericSubscription($workspace_uuid, $add_generic_subscription_request): object
```

Add generic subscription

Assigns a non-Stripe (generic) subscription plan to the workspace, optionally granting a trial period. Used for AppSumo-style lifetime deals. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$add_generic_subscription_request = new \PostBoostClient\Model\AddGenericSubscriptionRequest(); // \PostBoostClient\Model\AddGenericSubscriptionRequest

try {
    $result = $apiInstance->addGenericSubscription($workspace_uuid, $add_generic_subscription_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->addGenericSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **add_generic_subscription_request** | [**\PostBoostClient\Model\AddGenericSubscriptionRequest**](../Model/AddGenericSubscriptionRequest.md)|  | |

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

## `cancelSubscription()`

```php
cancelSubscription($workspace_uuid): object
```

Cancel subscription

Cancels the workspace's Stripe subscription at the end of the current billing period. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->cancelSubscription($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->cancelSubscription: ', $e->getMessage(), PHP_EOL;
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

## `changeSubscriptionPlan()`

```php
changeSubscriptionPlan($workspace_uuid, $change_subscription_plan_request): object
```

Change subscription plan

Switches the workspace to a different Stripe plan. Optionally prorates the change and bills immediately. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$change_subscription_plan_request = new \PostBoostClient\Model\ChangeSubscriptionPlanRequest(); // \PostBoostClient\Model\ChangeSubscriptionPlanRequest

try {
    $result = $apiInstance->changeSubscriptionPlan($workspace_uuid, $change_subscription_plan_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->changeSubscriptionPlan: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **change_subscription_plan_request** | [**\PostBoostClient\Model\ChangeSubscriptionPlanRequest**](../Model/ChangeSubscriptionPlanRequest.md)|  | |

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

## `checkoutSubscription()`

```php
checkoutSubscription($workspace_uuid, $checkout_subscription_request): \PostBoostClient\Model\CheckoutSubscription200Response
```

New subscription checkout

Returns a Stripe Checkout URL for a new subscription.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$checkout_subscription_request = new \PostBoostClient\Model\CheckoutSubscriptionRequest(); // \PostBoostClient\Model\CheckoutSubscriptionRequest

try {
    $result = $apiInstance->checkoutSubscription($workspace_uuid, $checkout_subscription_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->checkoutSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **checkout_subscription_request** | [**\PostBoostClient\Model\CheckoutSubscriptionRequest**](../Model/CheckoutSubscriptionRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\CheckoutSubscription200Response**](../Model/CheckoutSubscription200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createSubscription()`

```php
createSubscription($workspace_uuid, $subscription_input): object
```

Create subscription

Manually creates a subscription record for the workspace (for external billing integrations). Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$subscription_input = new \PostBoostClient\Model\SubscriptionInput(); // \PostBoostClient\Model\SubscriptionInput

try {
    $result = $apiInstance->createSubscription($workspace_uuid, $subscription_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->createSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **subscription_input** | [**\PostBoostClient\Model\SubscriptionInput**](../Model/SubscriptionInput.md)|  | |

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

## `deleteSubscription()`

```php
deleteSubscription($workspace_uuid): object
```

Delete subscription

Removes the subscription record from the workspace. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->deleteSubscription($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->deleteSubscription: ', $e->getMessage(), PHP_EOL;
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

## `getSubscription()`

```php
getSubscription($workspace_uuid): \PostBoostClient\Model\Subscription
```

Get subscription

Returns the active subscription for the workspace, or `null` if none exists. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->getSubscription($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->getSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\Subscription**](../Model/Subscription.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `removeGenericSubscription()`

```php
removeGenericSubscription($workspace_uuid): object
```

Remove generic subscription

Removes the generic (non-Stripe) subscription from the workspace. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->removeGenericSubscription($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->removeGenericSubscription: ', $e->getMessage(), PHP_EOL;
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

## `resumeSubscription()`

```php
resumeSubscription($workspace_uuid): object
```

Resume subscription

Resumes a previously canceled subscription before it expires. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->resumeSubscription($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->resumeSubscription: ', $e->getMessage(), PHP_EOL;
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

## `updateSubscription()`

```php
updateSubscription($workspace_uuid, $subscription_update_input): object
```

Update subscription

Updates the plan ID, status, or trial/pause dates of an existing subscription. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\SubscriptionsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$subscription_update_input = new \PostBoostClient\Model\SubscriptionUpdateInput(); // \PostBoostClient\Model\SubscriptionUpdateInput

try {
    $result = $apiInstance->updateSubscription($workspace_uuid, $subscription_update_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubscriptionsApi->updateSubscription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **subscription_update_input** | [**\PostBoostClient\Model\SubscriptionUpdateInput**](../Model/SubscriptionUpdateInput.md)|  | |

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
