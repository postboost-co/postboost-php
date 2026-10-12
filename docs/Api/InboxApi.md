# PostBoostClient\InboxApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**approveInboxReplyDraft()**](InboxApi.md#approveInboxReplyDraft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/approve | Approve and send a reply draft |
| [**createInboxReplyDraft()**](InboxApi.md#createInboxReplyDraft) | **POST** /{workspaceUuid}/inbox/conversations/{conversationId}/drafts | Draft a reply |
| [**deleteInboxReplyDraft()**](InboxApi.md#deleteInboxReplyDraft) | **DELETE** /{workspaceUuid}/inbox/drafts/{draftId} | Withdraw a reply draft |
| [**getInboxConversation()**](InboxApi.md#getInboxConversation) | **GET** /{workspaceUuid}/inbox/conversations/{conversationId} | Get an inbox conversation |
| [**getInboxReplyDraft()**](InboxApi.md#getInboxReplyDraft) | **GET** /{workspaceUuid}/inbox/drafts/{draftId} | Get a reply draft |
| [**listInboxConversations()**](InboxApi.md#listInboxConversations) | **GET** /{workspaceUuid}/inbox/conversations | List inbox conversations |
| [**listInboxReplyDrafts()**](InboxApi.md#listInboxReplyDrafts) | **GET** /{workspaceUuid}/inbox/drafts | List reply drafts |
| [**rejectInboxReplyDraft()**](InboxApi.md#rejectInboxReplyDraft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/reject | Reject a reply draft |
| [**updateInboxConversation()**](InboxApi.md#updateInboxConversation) | **PATCH** /{workspaceUuid}/inbox/conversations/{conversationId} | Update an inbox conversation |
| [**updateInboxReplyDraft()**](InboxApi.md#updateInboxReplyDraft) | **PUT** /{workspaceUuid}/inbox/drafts/{draftId} | Edit a reply draft |


## `approveInboxReplyDraft()`

```php
approveInboxReplyDraft($workspace_uuid, $draft_id, $inbox_reply_draft_approve): \PostBoostClient\Model\CreateInboxReplyDraft201Response
```

Approve and send a reply draft

Sends the draft to the network (optionally with an edited `body`). Ends as `sent`, or `failed` with `error`. Needs the `publish` ability; the API key that wrote the draft cannot approve it (`403`, `code: self_approval`). A draft is sent at most once: approving again returns `409`. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$draft_id = 'draft_id_example'; // string | The draft `id`.
$inbox_reply_draft_approve = new \PostBoostClient\Model\InboxReplyDraftApprove(); // \PostBoostClient\Model\InboxReplyDraftApprove

try {
    $result = $apiInstance->approveInboxReplyDraft($workspace_uuid, $draft_id, $inbox_reply_draft_approve);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->approveInboxReplyDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **draft_id** | **string**| The draft &#x60;id&#x60;. | |
| **inbox_reply_draft_approve** | [**\PostBoostClient\Model\InboxReplyDraftApprove**](../Model/InboxReplyDraftApprove.md)|  | [optional] |

### Return type

[**\PostBoostClient\Model\CreateInboxReplyDraft201Response**](../Model/CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createInboxReplyDraft()`

```php
createInboxReplyDraft($workspace_uuid, $conversation_id, $inbox_reply_draft_input): \PostBoostClient\Model\CreateInboxReplyDraft201Response
```

Draft a reply

Proposes a reply. Nothing is posted: a person approves the draft in the app (Reply drafts page) or another API key with the `publish` ability approves it. `in_reply_to` defaults to the latest incoming message. The body limit depends on the network (Bluesky 300, Mastodon 500, LinkedIn 1250, Google 4000). Needs the `write` ability. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$conversation_id = 'conversation_id_example'; // string | The conversation `id`.
$inbox_reply_draft_input = new \PostBoostClient\Model\InboxReplyDraftInput(); // \PostBoostClient\Model\InboxReplyDraftInput

try {
    $result = $apiInstance->createInboxReplyDraft($workspace_uuid, $conversation_id, $inbox_reply_draft_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->createInboxReplyDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **conversation_id** | **string**| The conversation &#x60;id&#x60;. | |
| **inbox_reply_draft_input** | [**\PostBoostClient\Model\InboxReplyDraftInput**](../Model/InboxReplyDraftInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateInboxReplyDraft201Response**](../Model/CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteInboxReplyDraft()`

```php
deleteInboxReplyDraft($workspace_uuid, $draft_id)
```

Withdraw a reply draft

Deletes a pending draft. `409` once it was reviewed. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$draft_id = 'draft_id_example'; // string | The draft `id`.

try {
    $apiInstance->deleteInboxReplyDraft($workspace_uuid, $draft_id);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->deleteInboxReplyDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **draft_id** | **string**| The draft &#x60;id&#x60;. | |

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

## `getInboxConversation()`

```php
getInboxConversation($workspace_uuid, $conversation_id): \PostBoostClient\Model\GetInboxConversation200Response
```

Get an inbox conversation

The conversation with its 50 most recent messages, oldest first. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$conversation_id = 'conversation_id_example'; // string | The conversation `id`.

try {
    $result = $apiInstance->getInboxConversation($workspace_uuid, $conversation_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->getInboxConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **conversation_id** | **string**| The conversation &#x60;id&#x60;. | |

### Return type

[**\PostBoostClient\Model\GetInboxConversation200Response**](../Model/GetInboxConversation200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getInboxReplyDraft()`

```php
getInboxReplyDraft($workspace_uuid, $draft_id): \PostBoostClient\Model\CreateInboxReplyDraft201Response
```

Get a reply draft

One draft. Poll it to see whether it was approved and sent. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$draft_id = 'draft_id_example'; // string | The draft `id`.

try {
    $result = $apiInstance->getInboxReplyDraft($workspace_uuid, $draft_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->getInboxReplyDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **draft_id** | **string**| The draft &#x60;id&#x60;. | |

### Return type

[**\PostBoostClient\Model\CreateInboxReplyDraft201Response**](../Model/CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listInboxConversations()`

```php
listInboxConversations($workspace_uuid, $status, $account_id, $provider, $unread, $sentiment, $ai_label, $since, $page): \PostBoostClient\Model\ListInboxConversations200Response
```

List inbox conversations

Comments, mentions and reviews on your accounts, most recent activity first, 25 per page. Available for Bluesky, Mastodon, LinkedIn Pages and Google Business Profile. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$status = 'status_example'; // string | Conversation status.
$account_id = 56; // int | Account `id`.
$provider = 'provider_example'; // string | Network, for example `bluesky`.
$unread = True; // bool | Only unread (`true`) or read (`false`) conversations.
$sentiment = 'sentiment_example'; // string | AI sentiment.
$ai_label = 'ai_label_example'; // string | AI label.
$since = new \DateTime("2013-10-20T19:20:30+01:00"); // \DateTime | Only conversations with activity at or after this time.
$page = 1; // int | Page number.

try {
    $result = $apiInstance->listInboxConversations($workspace_uuid, $status, $account_id, $provider, $unread, $sentiment, $ai_label, $since, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->listInboxConversations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **status** | **string**| Conversation status. | [optional] |
| **account_id** | **int**| Account &#x60;id&#x60;. | [optional] |
| **provider** | **string**| Network, for example &#x60;bluesky&#x60;. | [optional] |
| **unread** | **bool**| Only unread (&#x60;true&#x60;) or read (&#x60;false&#x60;) conversations. | [optional] |
| **sentiment** | **string**| AI sentiment. | [optional] |
| **ai_label** | **string**| AI label. | [optional] |
| **since** | **\DateTime**| Only conversations with activity at or after this time. | [optional] |
| **page** | **int**| Page number. | [optional] [default to 1] |

### Return type

[**\PostBoostClient\Model\ListInboxConversations200Response**](../Model/ListInboxConversations200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listInboxReplyDrafts()`

```php
listInboxReplyDrafts($workspace_uuid, $status, $conversation_id, $page): \PostBoostClient\Model\ListInboxReplyDrafts200Response
```

List reply drafts

Reply drafts, newest first, 25 per page. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$status = 'status_example'; // string | Draft status.
$conversation_id = 'conversation_id_example'; // string | Only drafts for this conversation `id`.
$page = 1; // int | Page number.

try {
    $result = $apiInstance->listInboxReplyDrafts($workspace_uuid, $status, $conversation_id, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->listInboxReplyDrafts: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **status** | **string**| Draft status. | [optional] |
| **conversation_id** | **string**| Only drafts for this conversation &#x60;id&#x60;. | [optional] |
| **page** | **int**| Page number. | [optional] [default to 1] |

### Return type

[**\PostBoostClient\Model\ListInboxReplyDrafts200Response**](../Model/ListInboxReplyDrafts200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `rejectInboxReplyDraft()`

```php
rejectInboxReplyDraft($workspace_uuid, $draft_id): \PostBoostClient\Model\CreateInboxReplyDraft201Response
```

Reject a reply draft

Rejects a pending draft; nothing is sent. Needs the `publish` ability. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$draft_id = 'draft_id_example'; // string | The draft `id`.

try {
    $result = $apiInstance->rejectInboxReplyDraft($workspace_uuid, $draft_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->rejectInboxReplyDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **draft_id** | **string**| The draft &#x60;id&#x60;. | |

### Return type

[**\PostBoostClient\Model\CreateInboxReplyDraft201Response**](../Model/CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateInboxConversation()`

```php
updateInboxConversation($workspace_uuid, $conversation_id, $inbox_conversation_update): \PostBoostClient\Model\GetInboxConversation200Response
```

Update an inbox conversation

Marks the conversation open or resolved, read or unread. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$conversation_id = 'conversation_id_example'; // string | The conversation `id`.
$inbox_conversation_update = new \PostBoostClient\Model\InboxConversationUpdate(); // \PostBoostClient\Model\InboxConversationUpdate

try {
    $result = $apiInstance->updateInboxConversation($workspace_uuid, $conversation_id, $inbox_conversation_update);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->updateInboxConversation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **conversation_id** | **string**| The conversation &#x60;id&#x60;. | |
| **inbox_conversation_update** | [**\PostBoostClient\Model\InboxConversationUpdate**](../Model/InboxConversationUpdate.md)|  | |

### Return type

[**\PostBoostClient\Model\GetInboxConversation200Response**](../Model/GetInboxConversation200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateInboxReplyDraft()`

```php
updateInboxReplyDraft($workspace_uuid, $draft_id, $inbox_reply_draft_edit): \PostBoostClient\Model\CreateInboxReplyDraft201Response
```

Edit a reply draft

Changes the text of a pending draft. `409` once it was reviewed. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\InboxApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$draft_id = 'draft_id_example'; // string | The draft `id`.
$inbox_reply_draft_edit = new \PostBoostClient\Model\InboxReplyDraftEdit(); // \PostBoostClient\Model\InboxReplyDraftEdit

try {
    $result = $apiInstance->updateInboxReplyDraft($workspace_uuid, $draft_id, $inbox_reply_draft_edit);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling InboxApi->updateInboxReplyDraft: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **draft_id** | **string**| The draft &#x60;id&#x60;. | |
| **inbox_reply_draft_edit** | [**\PostBoostClient\Model\InboxReplyDraftEdit**](../Model/InboxReplyDraftEdit.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateInboxReplyDraft201Response**](../Model/CreateInboxReplyDraft201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
