# PostBoostClient\TemplatesApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**createTemplate()**](TemplatesApi.md#createTemplate) | **POST** /{workspaceUuid}/templates | Create a template |
| [**deleteTemplate()**](TemplatesApi.md#deleteTemplate) | **DELETE** /{workspaceUuid}/templates/{templateId} | Delete a template |
| [**getTemplate()**](TemplatesApi.md#getTemplate) | **GET** /{workspaceUuid}/templates/{templateId} | Get a template |
| [**listTemplates()**](TemplatesApi.md#listTemplates) | **GET** /{workspaceUuid}/templates | List templates |
| [**updateTemplate()**](TemplatesApi.md#updateTemplate) | **PUT** /{workspaceUuid}/templates/{templateId} | Update a template |


## `createTemplate()`

```php
createTemplate($workspace_uuid, $template_input): \PostBoostClient\Model\CreateTemplate201Response
```

Create a template

Creates a post template: a name and one or more content items (body plus media ids from the media library). Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$template_input = new \PostBoostClient\Model\TemplateInput(); // \PostBoostClient\Model\TemplateInput

try {
    $result = $apiInstance->createTemplate($workspace_uuid, $template_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->createTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **template_input** | [**\PostBoostClient\Model\TemplateInput**](../Model/TemplateInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateTemplate201Response**](../Model/CreateTemplate201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteTemplate()`

```php
deleteTemplate($workspace_uuid, $template_id)
```

Delete a template

Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$template_id = 'template_id_example'; // string | The template `id`.

try {
    $apiInstance->deleteTemplate($workspace_uuid, $template_id);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->deleteTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **template_id** | **string**| The template &#x60;id&#x60;. | |

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

## `getTemplate()`

```php
getTemplate($workspace_uuid, $template_id): \PostBoostClient\Model\CreateTemplate201Response
```

Get a template

One template.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$template_id = 'template_id_example'; // string | The template `id`.

try {
    $result = $apiInstance->getTemplate($workspace_uuid, $template_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->getTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **template_id** | **string**| The template &#x60;id&#x60;. | |

### Return type

[**\PostBoostClient\Model\CreateTemplate201Response**](../Model/CreateTemplate201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listTemplates()`

```php
listTemplates($workspace_uuid, $page, $per_page): \PostBoostClient\Model\ListTemplates200Response
```

List templates

Post templates of the workspace, newest first. The same templates as the Templates page in the app. Paginated with `page` and `per_page` (default 100).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$page = 1; // int | Page number (1-based).
$per_page = 100; // int | Items per page, 1-100.

try {
    $result = $apiInstance->listTemplates($workspace_uuid, $page, $per_page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->listTemplates: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **page** | **int**| Page number (1-based). | [optional] [default to 1] |
| **per_page** | **int**| Items per page, 1-100. | [optional] [default to 100] |

### Return type

[**\PostBoostClient\Model\ListTemplates200Response**](../Model/ListTemplates200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateTemplate()`

```php
updateTemplate($workspace_uuid, $template_id, $template_input): \PostBoostClient\Model\CreateTemplate201Response
```

Update a template

Replaces the name and content of a template. Admins and members only (not viewers).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\TemplatesApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$template_id = 'template_id_example'; // string | The template `id`.
$template_input = new \PostBoostClient\Model\TemplateInput(); // \PostBoostClient\Model\TemplateInput

try {
    $result = $apiInstance->updateTemplate($workspace_uuid, $template_id, $template_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TemplatesApi->updateTemplate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **template_id** | **string**| The template &#x60;id&#x60;. | |
| **template_input** | [**\PostBoostClient\Model\TemplateInput**](../Model/TemplateInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateTemplate201Response**](../Model/CreateTemplate201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
