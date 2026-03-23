# PostBoostClient\ReceiptsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createReceipt()**](ReceiptsApi.md#createReceipt) | **POST** /panel/receipts | Create receipt |
| [**deleteReceipt()**](ReceiptsApi.md#deleteReceipt) | **DELETE** /panel/receipts/{receiptUuid} | Delete receipt |
| [**deleteReceiptsBulk()**](ReceiptsApi.md#deleteReceiptsBulk) | **DELETE** /panel/receipts | Delete receipts (bulk) |
| [**getReceipt()**](ReceiptsApi.md#getReceipt) | **GET** /panel/receipts/{receiptUuid} | Get receipt |
| [**listReceipts()**](ReceiptsApi.md#listReceipts) | **GET** /panel/receipts | List receipts |
| [**updateReceipt()**](ReceiptsApi.md#updateReceipt) | **PUT** /panel/receipts/{receiptUuid} | Update receipt |


## `createReceipt()`

```php
createReceipt($receipt_input): \PostBoostClient\Model\Receipt
```

Create receipt

Creates a billing receipt record for a workspace. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\ReceiptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$receipt_input = new \PostBoostClient\Model\ReceiptInput(); // \PostBoostClient\Model\ReceiptInput

try {
    $result = $apiInstance->createReceipt($receipt_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReceiptsApi->createReceipt: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **receipt_input** | [**\PostBoostClient\Model\ReceiptInput**](../Model/ReceiptInput.md)|  | |

### Return type

[**\PostBoostClient\Model\Receipt**](../Model/Receipt.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteReceipt()`

```php
deleteReceipt($receipt_uuid): object
```

Delete receipt

Permanently deletes a single receipt. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\ReceiptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$receipt_uuid = 'receipt_uuid_example'; // string | UUID of the receipt.

try {
    $result = $apiInstance->deleteReceipt($receipt_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReceiptsApi->deleteReceipt: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **receipt_uuid** | **string**| UUID of the receipt. | |

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

## `deleteReceiptsBulk()`

```php
deleteReceiptsBulk($delete_receipts_bulk_request): object
```

Delete receipts (bulk)

Permanently deletes one or more receipt records. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\ReceiptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$delete_receipts_bulk_request = new \PostBoostClient\Model\DeleteReceiptsBulkRequest(); // \PostBoostClient\Model\DeleteReceiptsBulkRequest

try {
    $result = $apiInstance->deleteReceiptsBulk($delete_receipts_bulk_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReceiptsApi->deleteReceiptsBulk: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **delete_receipts_bulk_request** | [**\PostBoostClient\Model\DeleteReceiptsBulkRequest**](../Model/DeleteReceiptsBulkRequest.md)|  | |

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

## `getReceipt()`

```php
getReceipt($receipt_uuid): \PostBoostClient\Model\Receipt
```

Get receipt

Returns a single receipt by UUID. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\ReceiptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$receipt_uuid = 'receipt_uuid_example'; // string | UUID of the receipt.

try {
    $result = $apiInstance->getReceipt($receipt_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReceiptsApi->getReceipt: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **receipt_uuid** | **string**| UUID of the receipt. | |

### Return type

[**\PostBoostClient\Model\Receipt**](../Model/Receipt.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listReceipts()`

```php
listReceipts($workspace_uuid, $invoice_number, $page): \PostBoostClient\Model\ListReceipts200Response
```

List receipts

Returns a paginated list of billing receipts. Filter by workspace UUID or invoice number. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\ReceiptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string
$invoice_number = 'invoice_number_example'; // string
$page = 1; // int | Page number (15 items per page).

try {
    $result = $apiInstance->listReceipts($workspace_uuid, $invoice_number, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReceiptsApi->listReceipts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**|  | [optional] |
| **invoice_number** | **string**|  | [optional] |
| **page** | **int**| Page number (15 items per page). | [optional] [default to 1] |

### Return type

[**\PostBoostClient\Model\ListReceipts200Response**](../Model/ListReceipts200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateReceipt()`

```php
updateReceipt($receipt_uuid, $receipt_update_input): object
```

Update receipt

Updates a receipt's transaction details, amount, or payment date. Admin only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\ReceiptsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$receipt_uuid = 'receipt_uuid_example'; // string | UUID of the receipt.
$receipt_update_input = new \PostBoostClient\Model\ReceiptUpdateInput(); // \PostBoostClient\Model\ReceiptUpdateInput

try {
    $result = $apiInstance->updateReceipt($receipt_uuid, $receipt_update_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ReceiptsApi->updateReceipt: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **receipt_uuid** | **string**| UUID of the receipt. | |
| **receipt_update_input** | [**\PostBoostClient\Model\ReceiptUpdateInput**](../Model/ReceiptUpdateInput.md)|  | |

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
