# PostBoostClient\PostsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**addPostToQueue()**](PostsApi.md#addPostToQueue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue |
| [**approvePost()**](PostsApi.md#approvePost) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post |
| [**createPost()**](PostsApi.md#createPost) | **POST** /{workspaceUuid}/posts | Create post |
| [**createRecyclingRule()**](PostsApi.md#createRecyclingRule) | **POST** /{workspaceUuid}/recycling-rules | Create a recycling rule |
| [**createRssFeed()**](PostsApi.md#createRssFeed) | **POST** /{workspaceUuid}/rss-feeds | Add an RSS feed |
| [**deletePost()**](PostsApi.md#deletePost) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post |
| [**deletePostsBulk()**](PostsApi.md#deletePostsBulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk) |
| [**deleteRecyclingRule()**](PostsApi.md#deleteRecyclingRule) | **DELETE** /{workspaceUuid}/recycling-rules/{ruleUuid} | Delete a recycling rule |
| [**deleteRssFeed()**](PostsApi.md#deleteRssFeed) | **DELETE** /{workspaceUuid}/rss-feeds/{feedUuid} | Delete an RSS feed |
| [**getPost()**](PostsApi.md#getPost) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post |
| [**getPostAnalytics()**](PostsApi.md#getPostAnalytics) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics |
| [**getRecyclingRule()**](PostsApi.md#getRecyclingRule) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid} | Get a recycling rule |
| [**getRssFeed()**](PostsApi.md#getRssFeed) | **GET** /{workspaceUuid}/rss-feeds/{feedUuid} | Get an RSS feed |
| [**listPosts()**](PostsApi.md#listPosts) | **GET** /{workspaceUuid}/posts | List posts |
| [**listRecyclingRules()**](PostsApi.md#listRecyclingRules) | **GET** /{workspaceUuid}/recycling-rules | List recycling rules |
| [**listRecyclingRuns()**](PostsApi.md#listRecyclingRuns) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid}/runs | List a recycling rule&#39;s runs |
| [**listRssFeeds()**](PostsApi.md#listRssFeeds) | **GET** /{workspaceUuid}/rss-feeds | List RSS feeds |
| [**pollRssFeed()**](PostsApi.md#pollRssFeed) | **POST** /{workspaceUuid}/rss-feeds/{feedUuid}/poll | Check an RSS feed now |
| [**recyclePost()**](PostsApi.md#recyclePost) | **POST** /{workspaceUuid}/posts/{postUuid}/recycle | Recycle a post on an interval |
| [**retryPostAccount()**](PostsApi.md#retryPostAccount) | **POST** /{workspaceUuid}/posts/retry/{postUuid}/{accountUuid} | Retry publishing to one account |
| [**schedulePost()**](PostsApi.md#schedulePost) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post |
| [**updatePost()**](PostsApi.md#updatePost) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post |
| [**updateRecyclingRule()**](PostsApi.md#updateRecyclingRule) | **PUT** /{workspaceUuid}/recycling-rules/{ruleUuid} | Update, pause or resume a recycling rule |
| [**updateRssFeed()**](PostsApi.md#updateRssFeed) | **PUT** /{workspaceUuid}/rss-feeds/{feedUuid} | Update, pause or resume an RSS feed |
| [**validatePost()**](PostsApi.md#validatePost) | **POST** /{workspaceUuid}/posts/validate | Validate post (dry run) |


## `addPostToQueue()`

```php
addPostToQueue($workspace_uuid, $post_uuid, $idempotency_key, $add_post_to_queue_request): \PostBoostClient\Model\ScheduleResult
```

Add post to queue

Add an existing post to the smart publishing queue. Each account of the post gets its own next free queue slot. Returns `422` when the post has no accounts, the posting schedule has no available times, or provider requirements are not met. The guardrails check the saved post as publishing at the queue slot it will get (the earliest next free slot of its accounts), as on create: `409` duplicate (override with `X-Allow-Duplicate: true`), `422` account cannot publish, `429` daily cap on that slot's UTC day or X cap.

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
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.
$add_post_to_queue_request = new \PostBoostClient\Model\AddPostToQueueRequest(); // \PostBoostClient\Model\AddPostToQueueRequest

try {
    $result = $apiInstance->addPostToQueue($workspace_uuid, $post_uuid, $idempotency_key, $add_post_to_queue_request);
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
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |
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
approvePost($workspace_uuid, $post_uuid, $idempotency_key, $approve_post_request): \PostBoostClient\Model\ScheduleResult
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
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.
$approve_post_request = new \PostBoostClient\Model\ApprovePostRequest(); // \PostBoostClient\Model\ApprovePostRequest

try {
    $result = $apiInstance->approvePost($workspace_uuid, $post_uuid, $idempotency_key, $approve_post_request);
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
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |
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
createPost($workspace_uuid, $post_input, $idempotency_key): \PostBoostClient\Model\CreatePost201Response
```

Create post

Create a new post. Use `schedule: true` with `date` and `time` to schedule, `schedule_now: true` to publish immediately, or `queue: true` to add to the smart publishing queue (each account gets its own queue slot).  `date`, `time` and `accounts_schedule` are read in `timezone` when given, otherwise in the workspace timezone. Use `accounts_schedule` to give individual accounts their own departure time.  Post bodies may reference mentions with `{{mention:<reference>}}` (see the Mentions endpoints). When the post is scheduled, provider requirements (for example a network that requires media) are validated up front and reported as `422`.  **First comment and threads.** A version's `content` is an ordered array. Item 0 is the post. Add a second item to publish a first comment on Facebook Page, Instagram and LinkedIn, or to continue a thread on X, Threads, Bluesky, Mastodon and Pixelfed:  ```json {   \"accounts\": [12],   \"schedule_now\": true,   \"versions\": [{     \"account_id\": 0,     \"is_original\": true,     \"content\": [       { \"body\": \"Our API 1.8 is live.\", \"media\": [345] },       { \"body\": \"Full changelog: https://postboost.co/docs/changelog/\" }     ]   }] } ```  The comment is posted right after the post goes live. If the comment fails, the post stays published and the account's entry on the post reports the error.

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
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.

try {
    $result = $apiInstance->createPost($workspace_uuid, $post_input, $idempotency_key);
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
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |

### Return type

[**\PostBoostClient\Model\CreatePost201Response**](../Model/CreatePost201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createRecyclingRule()`

```php
createRecyclingRule($workspace_uuid, $recycling_rule_input): \PostBoostClient\Model\CreateRecyclingRule201Response
```

Create a recycling rule

Recycles one post (`post_uuid`) or a tag pool (`type: tag_pool` + `tag_uuid`) every `interval_days`. The first run is `start_at`, or one interval from now. Copies are never published immediately: `placement: queue` (default) takes each account's next free queue slot, `same_time` schedules at the source post's time of day, `draft` leaves a draft.  Copies pass the same guardrails as posts created through the API (duplicate guard, per-account daily caps, disconnected accounts, X monthly allowance). A refused copy is not created; the run is logged with the guard's code (see the runs endpoint). X accounts are left out of copies because X rejects repeated text. Admins and members only.

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
$recycling_rule_input = {"post_uuid":"3f2b6c1e-8a4d-4f7e-9b2a-1c5d6e7f8a9b","interval_days":30,"max_runs":6,"placement":"queue"}; // \PostBoostClient\Model\RecyclingRuleInput

try {
    $result = $apiInstance->createRecyclingRule($workspace_uuid, $recycling_rule_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->createRecyclingRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **recycling_rule_input** | [**\PostBoostClient\Model\RecyclingRuleInput**](../Model/RecyclingRuleInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateRecyclingRule201Response**](../Model/CreateRecyclingRule201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createRssFeed()`

```php
createRssFeed($workspace_uuid, $rss_feed_input): \PostBoostClient\Model\CreateRssFeed201Response
```

Add an RSS feed

Checks the feed every 30 minutes and turns each item published after the feed was added into a post for `account_ids`: a draft (`mode: draft`, default), a queued post (`mode: queue`), or a queued post awaiting approval (`mode: needs_approval`: it gets the next free queue slot and publishes only after someone approves it). The text comes from `template` with `{title}`, `{link}` and `{summary}` placeholders. Each item becomes at most one post, at most `max_items_per_run` per check and 20 per workspace per day. Posts pass the same guardrails as API-created posts. Only public http(s) URLs are accepted. Admins and members only.

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
$rss_feed_input = {"url":"https://blog.example.com/feed","name":"Company blog","account_ids":[12,14],"mode":"draft","template":"New on the blog: {title} {link}"}; // \PostBoostClient\Model\RssFeedInput

try {
    $result = $apiInstance->createRssFeed($workspace_uuid, $rss_feed_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->createRssFeed: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **rss_feed_input** | [**\PostBoostClient\Model\RssFeedInput**](../Model/RssFeedInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateRssFeed201Response**](../Model/CreateRssFeed201Response.md)

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

## `deleteRecyclingRule()`

```php
deleteRecyclingRule($workspace_uuid, $rule_uuid): object
```

Delete a recycling rule

Deletes the rule and its run log. Copies it already created stay. Admins and members only.

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
$rule_uuid = 'rule_uuid_example'; // string | UUID of the recycling rule.

try {
    $result = $apiInstance->deleteRecyclingRule($workspace_uuid, $rule_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->deleteRecyclingRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **rule_uuid** | **string**| UUID of the recycling rule. | |

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

## `deleteRssFeed()`

```php
deleteRssFeed($workspace_uuid, $feed_uuid): object
```

Delete an RSS feed

Stops the feed. Posts it already created stay. Admins and members only.

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
$feed_uuid = 'feed_uuid_example'; // string | UUID of the RSS feed.

try {
    $result = $apiInstance->deleteRssFeed($workspace_uuid, $feed_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->deleteRssFeed: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **feed_uuid** | **string**| UUID of the RSS feed. | |

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

## `getRecyclingRule()`

```php
getRecyclingRule($workspace_uuid, $rule_uuid): \PostBoostClient\Model\CreateRecyclingRule201Response
```

Get a recycling rule

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
$rule_uuid = 'rule_uuid_example'; // string | UUID of the recycling rule.

try {
    $result = $apiInstance->getRecyclingRule($workspace_uuid, $rule_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->getRecyclingRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **rule_uuid** | **string**| UUID of the recycling rule. | |

### Return type

[**\PostBoostClient\Model\CreateRecyclingRule201Response**](../Model/CreateRecyclingRule201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRssFeed()`

```php
getRssFeed($workspace_uuid, $feed_uuid): \PostBoostClient\Model\CreateRssFeed201Response
```

Get an RSS feed

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
$feed_uuid = 'feed_uuid_example'; // string | UUID of the RSS feed.

try {
    $result = $apiInstance->getRssFeed($workspace_uuid, $feed_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->getRssFeed: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **feed_uuid** | **string**| UUID of the RSS feed. | |

### Return type

[**\PostBoostClient\Model\CreateRssFeed201Response**](../Model/CreateRssFeed201Response.md)

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

## `listRecyclingRules()`

```php
listRecyclingRules($workspace_uuid): \PostBoostClient\Model\ListRecyclingRules200Response
```

List recycling rules

Evergreen recycling rules of the workspace, newest first. A rule copies a post (or the least recently recycled published post with a tag) every `interval_days` and places the copy in the queue. Copies are ordinary posts: they show in the calendar and the queue.

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

try {
    $result = $apiInstance->listRecyclingRules($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->listRecyclingRules: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\ListRecyclingRules200Response**](../Model/ListRecyclingRules200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listRecyclingRuns()`

```php
listRecyclingRuns($workspace_uuid, $rule_uuid): \PostBoostClient\Model\ListRecyclingRuns200Response
```

List a recycling rule's runs

The latest 100 runs of the rule, newest first: the copy each run created, or why it skipped (`source_unavailable`, `no_eligible_post`, `no_accounts`, `queue_full`, `x_skipped_identical_text`, or a guardrail code such as `duplicate_post` or `account_daily_cap_reached`).

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
$rule_uuid = 'rule_uuid_example'; // string | UUID of the recycling rule.

try {
    $result = $apiInstance->listRecyclingRuns($workspace_uuid, $rule_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->listRecyclingRuns: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **rule_uuid** | **string**| UUID of the recycling rule. | |

### Return type

[**\PostBoostClient\Model\ListRecyclingRuns200Response**](../Model/ListRecyclingRuns200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listRssFeeds()`

```php
listRssFeeds($workspace_uuid): \PostBoostClient\Model\ListRssFeeds200Response
```

List RSS feeds

RSS and Atom feeds whose new items become posts, newest first.

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

try {
    $result = $apiInstance->listRssFeeds($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->listRssFeeds: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\ListRssFeeds200Response**](../Model/ListRssFeeds200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `pollRssFeed()`

```php
pollRssFeed($workspace_uuid, $feed_uuid): \PostBoostClient\Model\PollRssFeed200Response
```

Check an RSS feed now

Reads the feed immediately instead of waiting for the next check. Limited to 6 calls per minute. Admins and members only.

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
$feed_uuid = 'feed_uuid_example'; // string | UUID of the RSS feed.

try {
    $result = $apiInstance->pollRssFeed($workspace_uuid, $feed_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->pollRssFeed: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **feed_uuid** | **string**| UUID of the RSS feed. | |

### Return type

[**\PostBoostClient\Model\PollRssFeed200Response**](../Model/PollRssFeed200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `recyclePost()`

```php
recyclePost($workspace_uuid, $post_uuid, $recycling_rule_settings): \PostBoostClient\Model\CreateRecyclingRule201Response
```

Recycle a post on an interval

Shortcut for creating a `post` recycling rule for this post. Same body as `createRecyclingRule` without `type`, `post_uuid` and `tag_uuid`. Admins and members only.

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
$recycling_rule_settings = {"interval_days":14}; // \PostBoostClient\Model\RecyclingRuleSettings

try {
    $result = $apiInstance->recyclePost($workspace_uuid, $post_uuid, $recycling_rule_settings);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->recyclePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_uuid** | **string**| UUID of the post. | |
| **recycling_rule_settings** | [**\PostBoostClient\Model\RecyclingRuleSettings**](../Model/RecyclingRuleSettings.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateRecyclingRule201Response**](../Model/CreateRecyclingRule201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `retryPostAccount()`

```php
retryPostAccount($workspace_uuid, $post_uuid, $account_uuid, $idempotency_key): \PostBoostClient\Model\RetryPostAccountResult
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
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.

try {
    $result = $apiInstance->retryPostAccount($workspace_uuid, $post_uuid, $account_uuid, $idempotency_key);
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
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |

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
schedulePost($workspace_uuid, $post_uuid, $schedule_post_request, $idempotency_key): \PostBoostClient\Model\ScheduleResult
```

Schedule post

Schedule an existing post. Optionally move it with `date`/`time` (read in `timezone`) and give accounts their own times with `accounts_schedule`. Set `postNow: true` to publish immediately; publishing starts within the request and any per-account times are dropped. Provider requirements are validated and reported as `422`. The guardrails check the saved post at the time it would publish, as on create: `409` duplicate (override with `X-Allow-Duplicate: true`), `422` account cannot publish, `429` daily or X cap.

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
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.

try {
    $result = $apiInstance->schedulePost($workspace_uuid, $post_uuid, $schedule_post_request, $idempotency_key);
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
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |

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
updatePost($workspace_uuid, $post_uuid, $post_input): \PostBoostClient\Model\UpdatePost200Response
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

[**\PostBoostClient\Model\UpdatePost200Response**](../Model/UpdatePost200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateRecyclingRule()`

```php
updateRecyclingRule($workspace_uuid, $rule_uuid, $recycling_rule_update): \PostBoostClient\Model\CreateRecyclingRule201Response
```

Update, pause or resume a recycling rule

Changes the interval, limit, placement or accounts, or pauses (`active: false`) and resumes the rule. Fields you leave out keep their value. A rule that reached `max_runs` resumes only with a higher `max_runs`. Admins and members only.

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
$rule_uuid = 'rule_uuid_example'; // string | UUID of the recycling rule.
$recycling_rule_update = {"active":false}; // \PostBoostClient\Model\RecyclingRuleUpdate

try {
    $result = $apiInstance->updateRecyclingRule($workspace_uuid, $rule_uuid, $recycling_rule_update);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->updateRecyclingRule: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **rule_uuid** | **string**| UUID of the recycling rule. | |
| **recycling_rule_update** | [**\PostBoostClient\Model\RecyclingRuleUpdate**](../Model/RecyclingRuleUpdate.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateRecyclingRule201Response**](../Model/CreateRecyclingRule201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateRssFeed()`

```php
updateRssFeed($workspace_uuid, $feed_uuid, $rss_feed_update): \PostBoostClient\Model\CreateRssFeed201Response
```

Update, pause or resume an RSS feed

Fields you leave out keep their value. Resuming (`active: true`) clears the error backoff. Admins and members only.

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
$feed_uuid = 'feed_uuid_example'; // string | UUID of the RSS feed.
$rss_feed_update = {"active":false}; // \PostBoostClient\Model\RssFeedUpdate

try {
    $result = $apiInstance->updateRssFeed($workspace_uuid, $feed_uuid, $rss_feed_update);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->updateRssFeed: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **feed_uuid** | **string**| UUID of the RSS feed. | |
| **rss_feed_update** | [**\PostBoostClient\Model\RssFeedUpdate**](../Model/RssFeedUpdate.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateRssFeed201Response**](../Model/CreateRssFeed201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `validatePost()`

```php
validatePost($workspace_uuid, $post_input): \PostBoostClient\Model\PreflightResult
```

Validate post (dry run)

Runs everything create-post checks without creating anything: request validation, network requirements (text length, media count and type, links) for every given account, whether or not the post is scheduled, and the guardrails (duplicate content, daily caps, account health). Always answers `200`; read `valid`. `warnings` lists what create-post would return as warnings: what the network will reject or ignore at publish (for example a Threads post over 500 characters as Threads counts them). `valid` stays true for them; fix them before scheduling. Any workspace member, including viewers, may call it. Recommended agent loop: account health, validate, then create.

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
    $result = $apiInstance->validatePost($workspace_uuid, $post_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling PostsApi->validatePost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **post_input** | [**\PostBoostClient\Model\PostInput**](../Model/PostInput.md)|  | |

### Return type

[**\PostBoostClient\Model\PreflightResult**](../Model/PreflightResult.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
