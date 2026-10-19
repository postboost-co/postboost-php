# PostBoostClient\MediaApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**abortChunkedUpload()**](MediaApi.md#abortChunkedUpload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload |
| [**completeChunkedUpload()**](MediaApi.md#completeChunkedUpload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload |
| [**createMediaFolder()**](MediaApi.md#createMediaFolder) | **POST** /{workspaceUuid}/media/folders | Create media folder |
| [**deleteMediaBulk()**](MediaApi.md#deleteMediaBulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk) |
| [**deleteMediaFolder()**](MediaApi.md#deleteMediaFolder) | **DELETE** /{workspaceUuid}/media/folders/{folderUuid} | Delete media folder |
| [**getMedia()**](MediaApi.md#getMedia) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media |
| [**getRemoteUploadStatus()**](MediaApi.md#getRemoteUploadStatus) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status |
| [**initiateChunkedUpload()**](MediaApi.md#initiateChunkedUpload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload |
| [**initiateRemoteUpload()**](MediaApi.md#initiateRemoteUpload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload |
| [**listMedia()**](MediaApi.md#listMedia) | **GET** /{workspaceUuid}/media | List media |
| [**listMediaFolders()**](MediaApi.md#listMediaFolders) | **GET** /{workspaceUuid}/media/folders | List media folders |
| [**updateMedia()**](MediaApi.md#updateMedia) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media |
| [**updateMediaFolder()**](MediaApi.md#updateMediaFolder) | **PUT** /{workspaceUuid}/media/folders/{folderUuid} | Update media folder |
| [**uploadChunk()**](MediaApi.md#uploadChunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk |
| [**uploadMedia()**](MediaApi.md#uploadMedia) | **POST** /{workspaceUuid}/media | Upload media (binary) |
| [**uploadMediaBase64()**](MediaApi.md#uploadMediaBase64) | **POST** /{workspaceUuid}/media/base64 | Upload media (base64 JSON) |


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
completeChunkedUpload($workspace_uuid, $upload_uuid, $complete_chunked_upload_request): \PostBoostClient\Model\Media
```

Complete chunked upload

Signal that all chunks have been uploaded. Returns the final media object. A video may come back with `is_processing` set to `true` while its conversion runs.

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
$complete_chunked_upload_request = new \PostBoostClient\Model\CompleteChunkedUploadRequest(); // \PostBoostClient\Model\CompleteChunkedUploadRequest

try {
    $result = $apiInstance->completeChunkedUpload($workspace_uuid, $upload_uuid, $complete_chunked_upload_request);
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
| **complete_chunked_upload_request** | [**\PostBoostClient\Model\CompleteChunkedUploadRequest**](../Model/CompleteChunkedUploadRequest.md)|  | [optional] |

### Return type

[**\PostBoostClient\Model\Media**](../Model/Media.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createMediaFolder()`

```php
createMediaFolder($workspace_uuid, $create_media_folder_request, $idempotency_key): \PostBoostClient\Model\MediaFolder
```

Create media folder

Creates a folder at the top level or under `parent`. The name must be unique among its siblings.

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
$create_media_folder_request = new \PostBoostClient\Model\CreateMediaFolderRequest(); // \PostBoostClient\Model\CreateMediaFolderRequest
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.

try {
    $result = $apiInstance->createMediaFolder($workspace_uuid, $create_media_folder_request, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->createMediaFolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **create_media_folder_request** | [**\PostBoostClient\Model\CreateMediaFolderRequest**](../Model/CreateMediaFolderRequest.md)|  | |
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |

### Return type

[**\PostBoostClient\Model\MediaFolder**](../Model/MediaFolder.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteMediaBulk()`

```php
deleteMediaBulk($workspace_uuid, $delete_media_bulk_request): object
```

Delete media (bulk)

Delete one or more media items by their numeric IDs or UUIDs (both may be mixed, up to 500 per request).

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

## `deleteMediaFolder()`

```php
deleteMediaFolder($workspace_uuid, $folder_uuid, $delete_media_folder_request): object
```

Delete media folder

Deletes a folder. By default its media and sub-folders move up to the folder's parent; with `delete_media` set to true every media item below the folder is deleted as well.

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
$folder_uuid = 'folder_uuid_example'; // string | UUID of the media folder.
$delete_media_folder_request = new \PostBoostClient\Model\DeleteMediaFolderRequest(); // \PostBoostClient\Model\DeleteMediaFolderRequest

try {
    $result = $apiInstance->deleteMediaFolder($workspace_uuid, $folder_uuid, $delete_media_folder_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->deleteMediaFolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **folder_uuid** | **string**| UUID of the media folder. | |
| **delete_media_folder_request** | [**\PostBoostClient\Model\DeleteMediaFolderRequest**](../Model/DeleteMediaFolderRequest.md)|  | [optional] |

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

Poll a background download started by `initiateRemoteUpload` until `status` is `completed` or `failed`. `status` moves from `pending` to `downloading` and `processing`, and ends as `completed` (with `media`) or `failed` (with `error`). The final result is returned once: after a `completed` or `failed` response the download id is forgotten and later polls return `404`, as do ids older than one hour.

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
initiateChunkedUpload($workspace_uuid, $initiate_chunked_upload_request, $idempotency_key): \PostBoostClient\Model\InitiateChunkedUpload201Response
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
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.

try {
    $result = $apiInstance->initiateChunkedUpload($workspace_uuid, $initiate_chunked_upload_request, $idempotency_key);
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
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |

### Return type

[**\PostBoostClient\Model\InitiateChunkedUpload201Response**](../Model/InitiateChunkedUpload201Response.md)

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
initiateRemoteUpload($workspace_uuid, $initiate_remote_upload_request, $idempotency_key): \PostBoostClient\Model\InitiateRemoteUpload200Response
```

Initiate remote upload

Download a file from a remote URL into the media library. A file under 10 MB (or one whose server does not send its size) is downloaded during the request: the response has `status: completed` and the `media` object, or `status: failed` and an `error`. A larger file downloads in the background: the response has `status: pending` and a `download_id`; poll `getRemoteUploadStatus` with it until `status` is `completed` or `failed`.

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
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.

try {
    $result = $apiInstance->initiateRemoteUpload($workspace_uuid, $initiate_remote_upload_request, $idempotency_key);
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
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |

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
listMedia($workspace_uuid, $page, $limit, $folder, $mime_types, $type, $keyword, $usage, $favorite, $sort): \PostBoostClient\Model\ListMedia200Response
```

List media

Returns a paginated list of media assets in the workspace library. Without `folder` every item is listed, whatever folder it is filed in. A `keyword` search always looks at the whole library and ignores `folder` and `favorite`.

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
$page = 1; // int | Page number.
$limit = 50; // int | Items per page. Values below 1 fall back to 50; values above 100 are capped at 100.
$folder = 'folder_example'; // string | Media folder UUID, or `root` for items not filed in any folder.
$mime_types = array('mime_types_example'); // string[] | Only these MIME types (for example `image/png`).
$type = 'type_example'; // string | Only this media type.
$keyword = 'keyword_example'; // string | Search media by name.
$usage = 'usage_example'; // string | Filter by how the media is used in posts.
$favorite = True; // bool | When `true`, only media the caller marked as favorite.
$sort = 'newest'; // string

try {
    $result = $apiInstance->listMedia($workspace_uuid, $page, $limit, $folder, $mime_types, $type, $keyword, $usage, $favorite, $sort);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->listMedia: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **page** | **int**| Page number. | [optional] [default to 1] |
| **limit** | **int**| Items per page. Values below 1 fall back to 50; values above 100 are capped at 100. | [optional] [default to 50] |
| **folder** | **string**| Media folder UUID, or &#x60;root&#x60; for items not filed in any folder. | [optional] |
| **mime_types** | [**string[]**](../Model/string.md)| Only these MIME types (for example &#x60;image/png&#x60;). | [optional] |
| **type** | **string**| Only this media type. | [optional] |
| **keyword** | **string**| Search media by name. | [optional] |
| **usage** | **string**| Filter by how the media is used in posts. | [optional] |
| **favorite** | **bool**| When &#x60;true&#x60;, only media the caller marked as favorite. | [optional] |
| **sort** | **string**|  | [optional] [default to &#39;newest&#39;] |

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

## `listMediaFolders()`

```php
listMediaFolders($workspace_uuid): \PostBoostClient\Model\ListMediaFolders200Response
```

List media folders

Returns the whole folder tree of the media library in one response (not paginated). Rebuild the tree from each folder's `parent`.

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

try {
    $result = $apiInstance->listMediaFolders($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->listMediaFolders: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\ListMediaFolders200Response**](../Model/ListMediaFolders200Response.md)

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

Update the name, alt text, or folder of a media asset. Only the keys present in the body are written. Sending `folder: null` moves the item to the library root; omitting `folder` leaves it where it is.

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

## `updateMediaFolder()`

```php
updateMediaFolder($workspace_uuid, $folder_uuid, $media_folder_input): \PostBoostClient\Model\MediaFolder
```

Update media folder

Renames a folder and/or moves it. Sending `parent` moves the folder (null = top level); omitting it keeps the current parent. A folder cannot be moved into itself or one of its descendants.

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
$folder_uuid = 'folder_uuid_example'; // string | UUID of the media folder.
$media_folder_input = new \PostBoostClient\Model\MediaFolderInput(); // \PostBoostClient\Model\MediaFolderInput

try {
    $result = $apiInstance->updateMediaFolder($workspace_uuid, $folder_uuid, $media_folder_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->updateMediaFolder: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **folder_uuid** | **string**| UUID of the media folder. | |
| **media_folder_input** | [**\PostBoostClient\Model\MediaFolderInput**](../Model/MediaFolderInput.md)|  | |

### Return type

[**\PostBoostClient\Model\MediaFolder**](../Model/MediaFolder.md)

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
uploadChunk($workspace_uuid, $upload_uuid, $chunk, $chunk_index): \PostBoostClient\Model\UploadChunk201Response
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

[**\PostBoostClient\Model\UploadChunk201Response**](../Model/UploadChunk201Response.md)

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
uploadMedia($workspace_uuid, $file, $idempotency_key, $alt_text, $folder): \PostBoostClient\Model\Media
```

Upload media (binary)

Upload a file directly as multipart form data. Images and videos, plus a PDF (up to 100 MB) for LinkedIn document posts: a post that attaches a PDF must have it as the only media item and may only go to LinkedIn profiles and pages.

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
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.
$alt_text = 'alt_text_example'; // string | Alternative text for accessibility.
$folder = 'folder_example'; // string | UUID of the media folder to file the upload in. Omit or null for the library root.

try {
    $result = $apiInstance->uploadMedia($workspace_uuid, $file, $idempotency_key, $alt_text, $folder);
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
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |
| **alt_text** | **string**| Alternative text for accessibility. | [optional] |
| **folder** | **string**| UUID of the media folder to file the upload in. Omit or null for the library root. | [optional] |

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

## `uploadMediaBase64()`

```php
uploadMediaBase64($workspace_uuid, $media_base64_input, $idempotency_key): \PostBoostClient\Model\Media
```

Upload media (base64 JSON)

Upload a file as base64 inside a JSON body, for agents and tools that cannot send multipart form data. The decoded file is checked exactly like `POST media` (allowed types and size limits; a PDF is accepted for LinkedIn document posts). Decoded size is capped at 20 MB; for larger files use remote upload by URL or chunked upload.

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
$media_base64_input = new \PostBoostClient\Model\MediaBase64Input(); // \PostBoostClient\Model\MediaBase64Input
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.

try {
    $result = $apiInstance->uploadMediaBase64($workspace_uuid, $media_base64_input, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling MediaApi->uploadMediaBase64: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **media_base64_input** | [**\PostBoostClient\Model\MediaBase64Input**](../Model/MediaBase64Input.md)|  | |
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |

### Return type

[**\PostBoostClient\Model\Media**](../Model/Media.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
