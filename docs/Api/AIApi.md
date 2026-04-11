# PostBoostClient\AIApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**blogToSocial()**](AIApi.md#blogToSocial) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post |
| [**imageAltText()**](AIApi.md#imageAltText) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI |
| [**imageEdit()**](AIApi.md#imageEdit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI |
| [**imageGenerate()**](AIApi.md#imageGenerate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption |
| [**imagePrompt()**](AIApi.md#imagePrompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption |
| [**imageVariations()**](AIApi.md#imageVariations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image |


## `blogToSocial()`

```php
blogToSocial($workspace_uuid, $blog_to_social_input): \PostBoostClient\Model\BlogToSocial200Response
```

Generate social media captions from a blog post

Generates platform-specific social media captions from a blog post URL or directly provided title and excerpt. Each platform generates one caption, which consumes one AI credit from the workspace's monthly allowance.  **Input modes** (at least one required): - **URL mode**: provide `url` and the API scrapes the blog content automatically, including detecting the featured image via `og:image`. - **Direct mode**: provide `title` and `excerpt` directly (no scraping).  If both are provided, direct values take priority.  When `create_post` is `true`, a draft post is created in the workspace with per-account caption versions. If an image is available (from `image_url` or the scraped `og:image`), it is imported into the workspace media library and attached to the draft post.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$blog_to_social_input = {"url":"https://example.com/blog/my-post","platforms":["twitter","linkedin"],"tone":"professional","hashtags":"few","create_post":false}; // \PostBoostClient\Model\BlogToSocialInput

try {
    $result = $apiInstance->blogToSocial($workspace_uuid, $blog_to_social_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->blogToSocial: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **blog_to_social_input** | [**\PostBoostClient\Model\BlogToSocialInput**](../Model/BlogToSocialInput.md)|  | |

### Return type

[**\PostBoostClient\Model\BlogToSocial200Response**](../Model/BlogToSocial200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `imageAltText()`

```php
imageAltText($workspace_uuid, $image_alt_text_input): \PostBoostClient\Model\ImageAltText200Response
```

Generate alt text for a media image using AI

Analyzes an existing workspace media item and generates accessible alt text. The alt text is saved back to the media record. Costs 1 AI credit per call.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$image_alt_text_input = new \PostBoostClient\Model\ImageAltTextInput(); // \PostBoostClient\Model\ImageAltTextInput

try {
    $result = $apiInstance->imageAltText($workspace_uuid, $image_alt_text_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->imageAltText: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **image_alt_text_input** | [**\PostBoostClient\Model\ImageAltTextInput**](../Model/ImageAltTextInput.md)|  | |

### Return type

[**\PostBoostClient\Model\ImageAltText200Response**](../Model/ImageAltText200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `imageEdit()`

```php
imageEdit($workspace_uuid, $image_edit_input): \PostBoostClient\Model\ImageGenerate200Response
```

Edit an existing media image using AI

Edits an existing workspace media item using the source image and a text prompt. Optionally accepts a mask (transparent areas are replaced). Saves results to the media library. Credits: `count × credit_weight`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$image_edit_input = new \PostBoostClient\Model\ImageEditInput(); // \PostBoostClient\Model\ImageEditInput

try {
    $result = $apiInstance->imageEdit($workspace_uuid, $image_edit_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->imageEdit: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **image_edit_input** | [**\PostBoostClient\Model\ImageEditInput**](../Model/ImageEditInput.md)|  | |

### Return type

[**\PostBoostClient\Model\ImageGenerate200Response**](../Model/ImageGenerate200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `imageGenerate()`

```php
imageGenerate($workspace_uuid, $image_generate_input): \PostBoostClient\Model\ImageGenerate200Response
```

Generate social media images from a caption

Generates one or more images and saves them immediately to the workspace media library.  **Standard mode** (recommended): provide `caption` + `platform`. PostBoost builds a professional image prompt internally using platform-specific templates. No prompt engineering required.  **Developer mode**: provide `prompt` directly to bypass prompt building. If both `caption` and `prompt` are sent, standard mode runs.  Credits: `count x credit_weight` (default: 5 per image).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$image_generate_input = {"caption":"Our summer sale starts today, 30% off everything!","platform":"instagram","template":"product_highlight","aspect_ratio":"1:1","count":2}; // \PostBoostClient\Model\ImageGenerateInput

try {
    $result = $apiInstance->imageGenerate($workspace_uuid, $image_generate_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->imageGenerate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **image_generate_input** | [**\PostBoostClient\Model\ImageGenerateInput**](../Model/ImageGenerateInput.md)|  | |

### Return type

[**\PostBoostClient\Model\ImageGenerate200Response**](../Model/ImageGenerate200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `imagePrompt()`

```php
imagePrompt($workspace_uuid, $image_prompt_input): \PostBoostClient\Model\ImagePrompt200Response
```

Build an optimized image prompt from a social media caption

Builds a professional image generation prompt from a caption and platform. No image is generated. Use this to preview the prompt before calling `image-generate`. Costs 1 AI credit per call.  When `image-generate` builds the prompt internally (standard mode), no credit is charged for the prompt step.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$image_prompt_input = new \PostBoostClient\Model\ImagePromptInput(); // \PostBoostClient\Model\ImagePromptInput

try {
    $result = $apiInstance->imagePrompt($workspace_uuid, $image_prompt_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->imagePrompt: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **image_prompt_input** | [**\PostBoostClient\Model\ImagePromptInput**](../Model/ImagePromptInput.md)|  | |

### Return type

[**\PostBoostClient\Model\ImagePrompt200Response**](../Model/ImagePrompt200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `imageVariations()`

```php
imageVariations($workspace_uuid, $image_variations_input): \PostBoostClient\Model\ImageVariations200Response
```

Generate variations of an existing media image

Creates one or more variations of an existing workspace media item. Saves results to the media library. Credits: `count × credit_weight`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AIApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$image_variations_input = new \PostBoostClient\Model\ImageVariationsInput(); // \PostBoostClient\Model\ImageVariationsInput

try {
    $result = $apiInstance->imageVariations($workspace_uuid, $image_variations_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->imageVariations: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **image_variations_input** | [**\PostBoostClient\Model\ImageVariationsInput**](../Model/ImageVariationsInput.md)|  | |

### Return type

[**\PostBoostClient\Model\ImageVariations200Response**](../Model/ImageVariations200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
