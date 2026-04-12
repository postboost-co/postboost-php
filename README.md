# PostBoost PHP SDK

Official PHP client for the [PostBoost API](https://postboost.co/docs/api).

## Install

```bash
composer require postboost/php-sdk
```

| | |
|---|---|
| **Packagist** | [packagist.org/packages/postboost/php-sdk](https://packagist.org/packages/postboost/php-sdk) |
| **GitHub** | [postboost-co/postboost-php](https://github.com/postboost-co/postboost-php) |
| **Docs** | [postboost.co/docs/api](https://postboost.co/docs/api) |
| **Version** | v1.6.0 |

## Quick start

```php
use PostBoost\Client\Api\PostsApi;
use PostBoost\Client\Configuration;

$config = Configuration::getDefaultConfiguration()
    ->setAccessToken('YOUR_API_TOKEN');

$api = new PostsApi(new \GuzzleHttp\Client(), $config);
$posts = $api->listPosts('YOUR_WORKSPACE_UUID');
foreach ($posts as $post) {
    echo $post->getUuid() . PHP_EOL;
}
```

---

## API Endpoints

All URIs are relative to *https://postboost.co/app/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AIApi* | [**blogToSocial**](docs/Api/AIApi.md#blogtosocial) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post
*AIApi* | [**imageAltText**](docs/Api/AIApi.md#imagealttext) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI
*AIApi* | [**imageEdit**](docs/Api/AIApi.md#imageedit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI
*AIApi* | [**imageGenerate**](docs/Api/AIApi.md#imagegenerate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption
*AIApi* | [**imagePrompt**](docs/Api/AIApi.md#imageprompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption
*AIApi* | [**imageVariations**](docs/Api/AIApi.md#imagevariations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image
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
