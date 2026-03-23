# PostBoostClient\MediaApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**abortChunkedUpload()**](MediaApi.md#abortChunkedUpload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload |
| [**completeChunkedUpload()**](MediaApi.md#completeChunkedUpload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload |
| [**deleteMediaBulk()**](MediaApi.md#deleteMediaBulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk) |
| [**getMedia()**](MediaApi.md#getMedia) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media |
| [**getRemoteUploadStatus()**](MediaApi.md#getRemoteUploadStatus) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status |
| [**initiateChunkedUpload()**](MediaApi.md#initiateChunkedUpload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload |
| [**initiateRemoteUpload()**](MediaApi.md#initiateRemoteUpload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload |
| [**listMedia()**](MediaApi.md#listMedia) | **GET** /{workspaceUuid}/media | List media |
| [**updateMedia()**](MediaApi.md#updateMedia) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media |
| [**uploadChunk()**](MediaApi.md#uploadChunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk |
| [**uploadMedia()**](MediaApi.md#uploadMedia) | **POST** /{workspaceUuid}/media | Upload media (binary) |


## `abortChunkedUpload()`

```php
abortChunkedUpload($workspace_uuid, $upload_uuid)
```

Abort chunked upload

Cancel an in-progress chunked upload session and clean up uploaded chunks.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$upload_uuid = 'upload_uuid_example'; // string

try {
    $apiInstance->abortChunkedUpload($workspace_uuid, $upload_uuid);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->abortChunkedUpload: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **upload_uuid** | **string**|  | |

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

## `completeChunkedUpload()`

```php
completeChunkedUpload($workspace_uuid, $upload_uuid): \PostBoostClient\Model\Media
```

Complete chunked upload

Signal that all chunks have been uploaded. Returns the final media object.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$upload_uuid = 'upload_uuid_example'; // string

try {
    $result = $apiInstance->completeChunkedUpload($workspace_uuid, $upload_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->completeChunkedUpload: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **upload_uuid** | **string**|  | |

### Return type

[**\PostBoostClient\Model\Media**](../Model/Media.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteMediaBulk()`

```php
deleteMediaBulk($workspace_uuid, $delete_media_bulk_request): object
```

Delete media (bulk)

Delete one or more media items by their IDs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$delete_media_bulk_request = new \PostBoostClient\Model\DeleteMediaBulkRequest(); // \PostBoostClient\Model\DeleteMediaBulkRequest

try {
    $result = $apiInstance->deleteMediaBulk($workspace_uuid, $delete_media_bulk_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->deleteMediaBulk: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **delete_media_bulk_request** | [**\PostBoostClient\Model\DeleteMediaBulkRequest**](../Model/DeleteMediaBulkRequest.md)|  | |

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

## `getMedia()`

```php
getMedia($workspace_uuid, $media_uuid): \PostBoostClient\Model\Media
```

Get media

Returns a single media asset.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$media_uuid = 'media_uuid_example'; // string | UUID of the media asset.

try {
    $result = $apiInstance->getMedia($workspace_uuid, $media_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->getMedia: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **media_uuid** | **string**| UUID of the media asset. | |

### Return type

[**\PostBoostClient\Model\Media**](../Model/Media.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRemoteUploadStatus()`

```php
getRemoteUploadStatus($workspace_uuid, $download_id): \PostBoostClient\Model\GetRemoteUploadStatus200Response
```

Get remote upload status

Poll the status of an in-progress remote media download.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$download_id = 'download_id_example'; // string

try {
    $result = $apiInstance->getRemoteUploadStatus($workspace_uuid, $download_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->getRemoteUploadStatus: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **download_id** | **string**|  | |

### Return type

[**\PostBoostClient\Model\GetRemoteUploadStatus200Response**](../Model/GetRemoteUploadStatus200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `initiateChunkedUpload()`

```php
initiateChunkedUpload($workspace_uuid, $initiate_chunked_upload_request): \PostBoostClient\Model\InitiateChunkedUpload200Response
```

Initiate chunked upload

Start a chunked upload session for large files. Returns an `upload_uuid`, `chunk_size`, and `total_chunks` to use for subsequent chunk requests.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$initiate_chunked_upload_request = new \PostBoostClient\Model\InitiateChunkedUploadRequest(); // \PostBoostClient\Model\InitiateChunkedUploadRequest

try {
    $result = $apiInstance->initiateChunkedUpload($workspace_uuid, $initiate_chunked_upload_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->initiateChunkedUpload: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **initiate_chunked_upload_request** | [**\PostBoostClient\Model\InitiateChunkedUploadRequest**](../Model/InitiateChunkedUploadRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\InitiateChunkedUpload200Response**](../Model/InitiateChunkedUpload200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `initiateRemoteUpload()`

```php
initiateRemoteUpload($workspace_uuid, $initiate_remote_upload_request): \PostBoostClient\Model\InitiateRemoteUpload200Response
```

Initiate remote upload

Download a file from a remote URL into the media library. For small files the media object is returned immediately. For large files a `download_id` is returned — poll the status endpoint.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$initiate_remote_upload_request = new \PostBoostClient\Model\InitiateRemoteUploadRequest(); // \PostBoostClient\Model\InitiateRemoteUploadRequest

try {
    $result = $apiInstance->initiateRemoteUpload($workspace_uuid, $initiate_remote_upload_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->initiateRemoteUpload: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **initiate_remote_upload_request** | [**\PostBoostClient\Model\InitiateRemoteUploadRequest**](../Model/InitiateRemoteUploadRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\InitiateRemoteUpload200Response**](../Model/InitiateRemoteUpload200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listMedia()`

```php
listMedia($workspace_uuid, $page): \PostBoostClient\Model\ListMedia200Response
```

List media

Returns a paginated list of media assets in the workspace library.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$page = 1; // int | Page number (20 items per page).

try {
    $result = $apiInstance->listMedia($workspace_uuid, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->listMedia: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **page** | **int**| Page number (20 items per page). | [optional] [default to 1] |

### Return type

[**\PostBoostClient\Model\ListMedia200Response**](../Model/ListMedia200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateMedia()`

```php
updateMedia($workspace_uuid, $media_uuid, $update_media_request): object
```

Update media

Update the alt text of a media asset.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$media_uuid = 'media_uuid_example'; // string | UUID of the media asset.
$update_media_request = new \PostBoostClient\Model\UpdateMediaRequest(); // \PostBoostClient\Model\UpdateMediaRequest

try {
    $result = $apiInstance->updateMedia($workspace_uuid, $media_uuid, $update_media_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->updateMedia: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **media_uuid** | **string**| UUID of the media asset. | |
| **update_media_request** | [**\PostBoostClient\Model\UpdateMediaRequest**](../Model/UpdateMediaRequest.md)|  | |

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

## `uploadChunk()`

```php
uploadChunk($workspace_uuid, $upload_uuid, $chunk, $chunk_index): \PostBoostClient\Model\UploadChunk200Response
```

Upload a chunk

Upload a single chunk of a chunked upload session.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$upload_uuid = 'upload_uuid_example'; // string
$chunk = "/path/to/file.txt"; // \SplFileObject
$chunk_index = 56; // int | Zero-based index of this chunk.

try {
    $result = $apiInstance->uploadChunk($workspace_uuid, $upload_uuid, $chunk, $chunk_index);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->uploadChunk: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **upload_uuid** | **string**|  | |
| **chunk** | **\SplFileObject****\SplFileObject**|  | |
| **chunk_index** | **int**| Zero-based index of this chunk. | |

### Return type

[**\PostBoostClient\Model\UploadChunk200Response**](../Model/UploadChunk200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `uploadMedia()`

```php
uploadMedia($workspace_uuid, $file, $alt_text): \PostBoostClient\Model\Media
```

Upload media (binary)

Upload a file directly as multipart form data.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\MediaApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$file = "/path/to/file.txt"; // \SplFileObject | The file to upload.
$alt_text = 'alt_text_example'; // string | Alternative text for accessibility.

try {
    $result = $apiInstance->uploadMedia($workspace_uuid, $file, $alt_text);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->uploadMedia: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **file** | **\SplFileObject****\SplFileObject**| The file to upload. | |
| **alt_text** | **string**| Alternative text for accessibility. | [optional] |

### Return type

[**\PostBoostClient\Model\Media**](../Model/Media.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
