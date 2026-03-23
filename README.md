# PostBoostClient

The PostBoost REST API lets you publish, schedule, and analyze social media posts
across 8+ platforms from a single integration. No OAuth apps to maintain —
PostBoost handles platform authorization for you.

## Base URL
All workspace-scoped endpoints are prefixed with `/{workspaceUuid}`.
Panel/admin endpoints are prefixed with `/panel`.

## Authentication
All requests require a Bearer token in the `Authorization` header.
Generate tokens in your PostBoost dashboard under **Settings → Access Tokens**.

```
Authorization: Bearer YOUR_API_TOKEN
```


For more information, please visit [https://postboost.co](https://postboost.co).

## Installation & Usage

### Requirements

PHP 7.4 and later.
Should also work with PHP 8.0.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/GIT_USER_ID/GIT_REPO_ID.git"
    }
  ],
  "require": {
    "GIT_USER_ID/GIT_REPO_ID": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/PostBoostClient/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AccountsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$account_uuid = 'account_uuid_example'; // string | UUID of the social media account.

try {
    $result = $apiInstance->getAccount($workspace_uuid, $account_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountsApi->getAccount: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://postboost.co/app/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountsApi* | [**getAccount**](docs/Api/AccountsApi.md#getaccount) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
*AccountsApi* | [**listAccounts**](docs/Api/AccountsApi.md#listaccounts) | **GET** /{workspaceUuid}/accounts | List accounts
*MediaApi* | [**abortChunkedUpload**](docs/Api/MediaApi.md#abortchunkedupload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload
*MediaApi* | [**completeChunkedUpload**](docs/Api/MediaApi.md#completechunkedupload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload
*MediaApi* | [**deleteMediaBulk**](docs/Api/MediaApi.md#deletemediabulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk)
*MediaApi* | [**getMedia**](docs/Api/MediaApi.md#getmedia) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media
*MediaApi* | [**getRemoteUploadStatus**](docs/Api/MediaApi.md#getremoteuploadstatus) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status
*MediaApi* | [**initiateChunkedUpload**](docs/Api/MediaApi.md#initiatechunkedupload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload
*MediaApi* | [**initiateRemoteUpload**](docs/Api/MediaApi.md#initiateremoteupload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload
*MediaApi* | [**listMedia**](docs/Api/MediaApi.md#listmedia) | **GET** /{workspaceUuid}/media | List media
*MediaApi* | [**updateMedia**](docs/Api/MediaApi.md#updatemedia) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media
*MediaApi* | [**uploadChunk**](docs/Api/MediaApi.md#uploadchunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk
*MediaApi* | [**uploadMedia**](docs/Api/MediaApi.md#uploadmedia) | **POST** /{workspaceUuid}/media | Upload media (binary)
*PostsApi* | [**addPostToQueue**](docs/Api/PostsApi.md#addposttoqueue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
*PostsApi* | [**approvePost**](docs/Api/PostsApi.md#approvepost) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
*PostsApi* | [**createPost**](docs/Api/PostsApi.md#createpost) | **POST** /{workspaceUuid}/posts | Create post
*PostsApi* | [**deletePost**](docs/Api/PostsApi.md#deletepost) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
*PostsApi* | [**deletePostsBulk**](docs/Api/PostsApi.md#deletepostsbulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
*PostsApi* | [**getPost**](docs/Api/PostsApi.md#getpost) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
*PostsApi* | [**listPosts**](docs/Api/PostsApi.md#listposts) | **GET** /{workspaceUuid}/posts | List posts
*PostsApi* | [**schedulePost**](docs/Api/PostsApi.md#schedulepost) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
*PostsApi* | [**updatePost**](docs/Api/PostsApi.md#updatepost) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post
*ReceiptsApi* | [**createReceipt**](docs/Api/ReceiptsApi.md#createreceipt) | **POST** /panel/receipts | Create receipt
*ReceiptsApi* | [**deleteReceipt**](docs/Api/ReceiptsApi.md#deletereceipt) | **DELETE** /panel/receipts/{receiptUuid} | Delete receipt
*ReceiptsApi* | [**deleteReceiptsBulk**](docs/Api/ReceiptsApi.md#deletereceiptsbulk) | **DELETE** /panel/receipts | Delete receipts (bulk)
*ReceiptsApi* | [**getReceipt**](docs/Api/ReceiptsApi.md#getreceipt) | **GET** /panel/receipts/{receiptUuid} | Get receipt
*ReceiptsApi* | [**listReceipts**](docs/Api/ReceiptsApi.md#listreceipts) | **GET** /panel/receipts | List receipts
*ReceiptsApi* | [**updateReceipt**](docs/Api/ReceiptsApi.md#updatereceipt) | **PUT** /panel/receipts/{receiptUuid} | Update receipt
*SubscriptionsApi* | [**addGenericSubscription**](docs/Api/SubscriptionsApi.md#addgenericsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/generic | Add generic subscription
*SubscriptionsApi* | [**cancelSubscription**](docs/Api/SubscriptionsApi.md#cancelsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/cancel | Cancel subscription
*SubscriptionsApi* | [**changeSubscriptionPlan**](docs/Api/SubscriptionsApi.md#changesubscriptionplan) | **PUT** /panel/workspaces/{workspaceUuid}/subscription/change-plan | Change subscription plan
*SubscriptionsApi* | [**checkoutSubscription**](docs/Api/SubscriptionsApi.md#checkoutsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/new | New subscription checkout
*SubscriptionsApi* | [**createSubscription**](docs/Api/SubscriptionsApi.md#createsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription | Create subscription
*SubscriptionsApi* | [**deleteSubscription**](docs/Api/SubscriptionsApi.md#deletesubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription | Delete subscription
*SubscriptionsApi* | [**getSubscription**](docs/Api/SubscriptionsApi.md#getsubscription) | **GET** /panel/workspaces/{workspaceUuid}/subscription | Get subscription
*SubscriptionsApi* | [**removeGenericSubscription**](docs/Api/SubscriptionsApi.md#removegenericsubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription/generic | Remove generic subscription
*SubscriptionsApi* | [**resumeSubscription**](docs/Api/SubscriptionsApi.md#resumesubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/resume | Resume subscription
*SubscriptionsApi* | [**updateSubscription**](docs/Api/SubscriptionsApi.md#updatesubscription) | **PUT** /panel/workspaces/{workspaceUuid}/subscription | Update subscription
*TagsApi* | [**createTag**](docs/Api/TagsApi.md#createtag) | **POST** /{workspaceUuid}/tags | Create tag
*TagsApi* | [**deleteTag**](docs/Api/TagsApi.md#deletetag) | **DELETE** /{workspaceUuid}/tags/{tagUuid} | Delete tag
*TagsApi* | [**getTag**](docs/Api/TagsApi.md#gettag) | **GET** /{workspaceUuid}/tags/{tagUuid} | Get tag
*TagsApi* | [**listTags**](docs/Api/TagsApi.md#listtags) | **GET** /{workspaceUuid}/tags | List tags
*TagsApi* | [**updateTag**](docs/Api/TagsApi.md#updatetag) | **PUT** /{workspaceUuid}/tags/{tagUuid} | Update tag
*UsersApi* | [**createUser**](docs/Api/UsersApi.md#createuser) | **POST** /panel/users | Create user
*UsersApi* | [**deleteUser**](docs/Api/UsersApi.md#deleteuser) | **DELETE** /panel/users/{userId} | Delete user
*UsersApi* | [**deleteUsersBulk**](docs/Api/UsersApi.md#deleteusersbulk) | **DELETE** /panel/users | Delete users (bulk)
*UsersApi* | [**getUser**](docs/Api/UsersApi.md#getuser) | **GET** /panel/users/{userId} | Get user
*UsersApi* | [**listUsers**](docs/Api/UsersApi.md#listusers) | **GET** /panel/users | List users
*UsersApi* | [**updateUser**](docs/Api/UsersApi.md#updateuser) | **PUT** /panel/users/{userId} | Update user
*WorkspacesApi* | [**addUserToWorkspace**](docs/Api/WorkspacesApi.md#addusertoworkspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
*WorkspacesApi* | [**createWorkspace**](docs/Api/WorkspacesApi.md#createworkspace) | **POST** /panel/workspaces | Create workspace
*WorkspacesApi* | [**deleteWorkspace**](docs/Api/WorkspacesApi.md#deleteworkspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
*WorkspacesApi* | [**deleteWorkspacesBulk**](docs/Api/WorkspacesApi.md#deleteworkspacesbulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
*WorkspacesApi* | [**getWorkspace**](docs/Api/WorkspacesApi.md#getworkspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
*WorkspacesApi* | [**listWorkspaces**](docs/Api/WorkspacesApi.md#listworkspaces) | **GET** /panel/workspaces | List workspaces
*WorkspacesApi* | [**removeUserFromWorkspace**](docs/Api/WorkspacesApi.md#removeuserfromworkspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
*WorkspacesApi* | [**updateWorkspace**](docs/Api/WorkspacesApi.md#updateworkspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
*WorkspacesApi* | [**updateWorkspaceUser**](docs/Api/WorkspacesApi.md#updateworkspaceuser) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace

## Models

- [Account](docs/Model/Account.md)
- [AddGenericSubscriptionRequest](docs/Model/AddGenericSubscriptionRequest.md)
- [ChangeSubscriptionPlanRequest](docs/Model/ChangeSubscriptionPlanRequest.md)
- [CheckoutSubscription200Response](docs/Model/CheckoutSubscription200Response.md)
- [CheckoutSubscriptionRequest](docs/Model/CheckoutSubscriptionRequest.md)
- [DeleteMediaBulkRequest](docs/Model/DeleteMediaBulkRequest.md)
- [DeleteMode](docs/Model/DeleteMode.md)
- [DeletePostRequest](docs/Model/DeletePostRequest.md)
- [DeletePostsBulkRequest](docs/Model/DeletePostsBulkRequest.md)
- [DeleteReceiptsBulkRequest](docs/Model/DeleteReceiptsBulkRequest.md)
- [DeleteResult](docs/Model/DeleteResult.md)
- [DeleteUser400Response](docs/Model/DeleteUser400Response.md)
- [DeleteUsersBulkRequest](docs/Model/DeleteUsersBulkRequest.md)
- [DeleteWorkspacesBulkRequest](docs/Model/DeleteWorkspacesBulkRequest.md)
- [GetRemoteUploadStatus200Response](docs/Model/GetRemoteUploadStatus200Response.md)
- [InitiateChunkedUpload200Response](docs/Model/InitiateChunkedUpload200Response.md)
- [InitiateChunkedUploadRequest](docs/Model/InitiateChunkedUploadRequest.md)
- [InitiateRemoteUpload200Response](docs/Model/InitiateRemoteUpload200Response.md)
- [InitiateRemoteUpload200ResponseOneOf](docs/Model/InitiateRemoteUpload200ResponseOneOf.md)
- [InitiateRemoteUploadRequest](docs/Model/InitiateRemoteUploadRequest.md)
- [ListAccounts200Response](docs/Model/ListAccounts200Response.md)
- [ListMedia200Response](docs/Model/ListMedia200Response.md)
- [ListPosts200Response](docs/Model/ListPosts200Response.md)
- [ListReceipts200Response](docs/Model/ListReceipts200Response.md)
- [ListTags200Response](docs/Model/ListTags200Response.md)
- [ListUsers200Response](docs/Model/ListUsers200Response.md)
- [ListWorkspaces200Response](docs/Model/ListWorkspaces200Response.md)
- [Media](docs/Model/Media.md)
- [PaginationMeta](docs/Model/PaginationMeta.md)
- [PaginationMetaLinks](docs/Model/PaginationMetaLinks.md)
- [PaginationMetaMeta](docs/Model/PaginationMetaMeta.md)
- [Post](docs/Model/Post.md)
- [PostContent](docs/Model/PostContent.md)
- [PostInput](docs/Model/PostInput.md)
- [PostStatus](docs/Model/PostStatus.md)
- [PostVersion](docs/Model/PostVersion.md)
- [Receipt](docs/Model/Receipt.md)
- [ReceiptInput](docs/Model/ReceiptInput.md)
- [ReceiptUpdateInput](docs/Model/ReceiptUpdateInput.md)
- [RemoveUserFromWorkspaceRequest](docs/Model/RemoveUserFromWorkspaceRequest.md)
- [SchedulePostRequest](docs/Model/SchedulePostRequest.md)
- [ScheduleResult](docs/Model/ScheduleResult.md)
- [Subscription](docs/Model/Subscription.md)
- [SubscriptionInput](docs/Model/SubscriptionInput.md)
- [SubscriptionStatus](docs/Model/SubscriptionStatus.md)
- [SubscriptionUpdateInput](docs/Model/SubscriptionUpdateInput.md)
- [Tag](docs/Model/Tag.md)
- [TagInput](docs/Model/TagInput.md)
- [UpdateMediaRequest](docs/Model/UpdateMediaRequest.md)
- [UploadChunk200Response](docs/Model/UploadChunk200Response.md)
- [User](docs/Model/User.md)
- [UserInput](docs/Model/UserInput.md)
- [UserUpdateInput](docs/Model/UserUpdateInput.md)
- [Workspace](docs/Model/Workspace.md)
- [WorkspaceInput](docs/Model/WorkspaceInput.md)
- [WorkspaceUserInput](docs/Model/WorkspaceUserInput.md)

## Authorization

Authentication schemes defined for the API:
### bearerAuth

- **Type**: Bearer authentication

## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author

hi@postboost.co

## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.0.0`
    - Generator version: `7.9.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`
