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
| [**getPostAnalytics()**](PostsApi.md#getPostAnalytics) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics |
| [**listPosts()**](PostsApi.md#listPosts) | **GET** /{workspaceUuid}/posts | List posts |
| [**retryPostAccount()**](PostsApi.md#retryPostAccount) | **POST** /{workspaceUuid}/posts/retry/{postUuid}/{accountUuid} | Retry publishing to one account |
| [**schedulePost()**](PostsApi.md#schedulePost) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post |
| [**updatePost()**](PostsApi.md#updatePost) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post |


## `addPostToQueue()`

```php
addPostToQueue($workspace_uuid, $post_uuid, $add_post_to_queue_request): \PostBoostClient\Model\ScheduleResult
```

Add post to queue

Add an existing post to the smart publishing queue. Each account of the post gets its own next free queue slot. Returns `422` when the post has no accounts, the posting schedule has no available times, or provider requirements are not met.

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
$add_post_to_queue_request = new \PostBoostClient\Model\AddPostToQueueRequest(); // \PostBoostClient\Model\AddPostToQueueRequest

try {
    $result = $apiInstance->addPostToQueue($workspace_uuid, $post_uuid, $add_post_to_queue_request);
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
| **add_post_to_queue_request** | [**\PostBoostClient\Model\AddPostToQueueRequest**](../Model/AddPostToQueueRequest.md)|  | [optional] |

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

## `approvePost()`

```php
approvePost($workspace_uuid, $post_uuid, $approve_post_request): \PostBoostClient\Model\ScheduleResult
```

Approve post

Approve a post that is pending review. The approver may move the post with `date`/`time` (read in `timezone`) and set per-account times with `accounts_schedule`; without them the post keeps the time it was submitted with. Provider requirements are validated and reported as `422`.

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
$approve_post_request = new \PostBoostClient\Model\ApprovePostRequest(); // \PostBoostClient\Model\ApprovePostRequest

try {
    $result = $apiInstance->approvePost($workspace_uuid, $post_uuid, $approve_post_request);
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
| **approve_post_request** | [**\PostBoostClient\Model\ApprovePostRequest**](../Model/ApprovePostRequest.md)|  | [optional] |

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

## `createPost()`

```php
createPost($workspace_uuid, $post_input): \PostBoostClient\Model\Post
```

Create post

Create a new post. Use `schedule: true` with `date` and `time` to schedule, `schedule_now: true` to publish immediately, or `queue: true` to add to the smart publishing queue (each account gets its own queue slot).  `date`, `time` and `accounts_schedule` are read in `timezone` when given, otherwise in the workspace timezone. Use `accounts_schedule` to give individual accounts their own departure time.  Post bodies may reference mentions with `{{mention:<reference>}}` (see the Mentions endpoints). When the post is scheduled, provider requirements (for example a network that requires media) are validated up front and reported as `422`.

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

## `getPostAnalytics()`

```php
getPostAnalytics($workspace_uuid, $post_uuid): \PostBoostClient\Model\PostAnalytics
```

Get post analytics

Engagement metrics for a published post across its accounts (also works for trashed posts), with totals, trends and the best-performing account.

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
    $result = $apiInstance->getPostAnalytics($workspace_uuid, $post_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->getPostAnalytics: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |

### Return type

[**\PostBoostClient\Model\PostAnalytics**](../Model/PostAnalytics.md)

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

## `retryPostAccount()`

```php
retryPostAccount($workspace_uuid, $post_uuid, $account_uuid): \PostBoostClient\Model\RetryPostAccountResult
```

Retry publishing to one account

Re-publishes a post to a single account whose publishing failed. Returns `422` when the account is not on the post, the post is still publishing, or the account did not fail.

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
$account_uuid = 'account_uuid_example'; // string | UUID of the social media account.

try {
    $result = $apiInstance->retryPostAccount($workspace_uuid, $post_uuid, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->retryPostAccount: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |
| **account_uuid** | **string**| UUID of the social media account. | |

### Return type

[**\PostBoostClient\Model\RetryPostAccountResult**](../Model/RetryPostAccountResult.md)

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

Schedule an existing post. Optionally move it with `date`/`time` (read in `timezone`) and give accounts their own times with `accounts_schedule`. Set `postNow: true` to publish immediately; publishing starts within the request and any per-account times are dropped. Provider requirements are validated and reported as `422`.

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

Replaces a post's versions, accounts, tags, and scheduling options. The post must not be in a published state. `timezone` is honoured: `date`, `time` and `accounts_schedule` are read in it. When the post stays scheduled, provider requirements are validated and reported as `422`.

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
