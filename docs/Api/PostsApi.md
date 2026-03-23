# PostBoostClient\PostsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addPostToQueue()**](PostsApi.md#addPostToQueue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue |
| [**approvePost()**](PostsApi.md#approvePost) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post |
| [**createPost()**](PostsApi.md#createPost) | **POST** /{workspaceUuid}/posts | Create post |
| [**deletePost()**](PostsApi.md#deletePost) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post |
| [**deletePostsBulk()**](PostsApi.md#deletePostsBulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk) |
| [**getPost()**](PostsApi.md#getPost) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post |
| [**listPosts()**](PostsApi.md#listPosts) | **GET** /{workspaceUuid}/posts | List posts |
| [**schedulePost()**](PostsApi.md#schedulePost) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post |
| [**updatePost()**](PostsApi.md#updatePost) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post |


## `addPostToQueue()`

```php
addPostToQueue($workspace_uuid, $post_uuid): \PostBoostClient\Model\ScheduleResult
```

Add post to queue

Add an existing post to the smart publishing queue.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$post_uuid = 'post_uuid_example'; // string | UUID of the post.

try {
    $result = $apiInstance->addPostToQueue($workspace_uuid, $post_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->addPostToQueue: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |

### Return type

[**\PostBoostClient\Model\ScheduleResult**](../Model/ScheduleResult.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `approvePost()`

```php
approvePost($workspace_uuid, $post_uuid): \PostBoostClient\Model\ScheduleResult
```

Approve post

Approve a post that is pending review.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$post_uuid = 'post_uuid_example'; // string | UUID of the post.

try {
    $result = $apiInstance->approvePost($workspace_uuid, $post_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->approvePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |

### Return type

[**\PostBoostClient\Model\ScheduleResult**](../Model/ScheduleResult.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createPost()`

```php
createPost($workspace_uuid, $post_input): \PostBoostClient\Model\Post
```

Create post

Create a new post. Use `schedule: true` with `date` and `time` to schedule, `schedule_now: true` to publish immediately, or `queue: true` to add to the smart publishing queue.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$post_input = new \PostBoostClient\Model\PostInput(); // \PostBoostClient\Model\PostInput

try {
    $result = $apiInstance->createPost($workspace_uuid, $post_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->createPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_input** | [**\PostBoostClient\Model\PostInput**](../Model/PostInput.md)|  | |

### Return type

[**\PostBoostClient\Model\Post**](../Model/Post.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deletePost()`

```php
deletePost($workspace_uuid, $post_uuid, $delete_post_request): \PostBoostClient\Model\DeleteResult
```

Delete post

Deletes a post. Use `delete_mode` to control whether to also remove the published content from social platforms.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$post_uuid = 'post_uuid_example'; // string | UUID of the post.
$delete_post_request = new \PostBoostClient\Model\DeletePostRequest(); // \PostBoostClient\Model\DeletePostRequest

try {
    $result = $apiInstance->deletePost($workspace_uuid, $post_uuid, $delete_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->deletePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |
| **delete_post_request** | [**\PostBoostClient\Model\DeletePostRequest**](../Model/DeletePostRequest.md)|  | [optional] |

### Return type

[**\PostBoostClient\Model\DeleteResult**](../Model/DeleteResult.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deletePostsBulk()`

```php
deletePostsBulk($workspace_uuid, $delete_posts_bulk_request): \PostBoostClient\Model\DeleteResult
```

Delete posts (bulk)

Delete multiple posts at once.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$delete_posts_bulk_request = new \PostBoostClient\Model\DeletePostsBulkRequest(); // \PostBoostClient\Model\DeletePostsBulkRequest

try {
    $result = $apiInstance->deletePostsBulk($workspace_uuid, $delete_posts_bulk_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->deletePostsBulk: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **delete_posts_bulk_request** | [**\PostBoostClient\Model\DeletePostsBulkRequest**](../Model/DeletePostsBulkRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\DeleteResult**](../Model/DeleteResult.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getPost()`

```php
getPost($workspace_uuid, $post_uuid): \PostBoostClient\Model\Post
```

Get post

Returns a single post with all its versions and associated accounts.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$post_uuid = 'post_uuid_example'; // string | UUID of the post.

try {
    $result = $apiInstance->getPost($workspace_uuid, $post_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->getPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |

### Return type

[**\PostBoostClient\Model\Post**](../Model/Post.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listPosts()`

```php
listPosts($workspace_uuid, $page): \PostBoostClient\Model\ListPosts200Response
```

List posts

Returns a paginated list of posts in the workspace.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$page = 1; // int

try {
    $result = $apiInstance->listPosts($workspace_uuid, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->listPosts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **page** | **int**|  | [optional] [default to 1] |

### Return type

[**\PostBoostClient\Model\ListPosts200Response**](../Model/ListPosts200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `schedulePost()`

```php
schedulePost($workspace_uuid, $post_uuid, $schedule_post_request): \PostBoostClient\Model\ScheduleResult
```

Schedule post

Schedule an existing post. Set `postNow: true` to publish immediately.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$post_uuid = 'post_uuid_example'; // string | UUID of the post.
$schedule_post_request = new \PostBoostClient\Model\SchedulePostRequest(); // \PostBoostClient\Model\SchedulePostRequest

try {
    $result = $apiInstance->schedulePost($workspace_uuid, $post_uuid, $schedule_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->schedulePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |
| **schedule_post_request** | [**\PostBoostClient\Model\SchedulePostRequest**](../Model/SchedulePostRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\ScheduleResult**](../Model/ScheduleResult.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updatePost()`

```php
updatePost($workspace_uuid, $post_uuid, $post_input): object
```

Update post

Replaces a post's versions, accounts, tags, and scheduling options. The post must not be in a published state.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\PostsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$post_uuid = 'post_uuid_example'; // string | UUID of the post.
$post_input = new \PostBoostClient\Model\PostInput(); // \PostBoostClient\Model\PostInput

try {
    $result = $apiInstance->updatePost($workspace_uuid, $post_uuid, $post_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->updatePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |
| **post_input** | [**\PostBoostClient\Model\PostInput**](../Model/PostInput.md)|  | |

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
