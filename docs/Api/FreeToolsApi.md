# PostBoostClient\FreeToolsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**buildUtmUrl()**](FreeToolsApi.md#buildUtmUrl) | **POST** /tools/utm-builder | Build a UTM-tagged campaign URL |
| [**calculateAspectRatio()**](FreeToolsApi.md#calculateAspectRatio) | **POST** /tools/aspect-ratio-calculator | Calculate an aspect ratio, or the missing side of an image at a given ratio |
| [**calculateCrop()**](FreeToolsApi.md#calculateCrop) | **POST** /tools/social-media-image-sizes/crop | Calculate the crop box that fits an image to a social media size |
| [**calculateEngagementRate()**](FreeToolsApi.md#calculateEngagementRate) | **POST** /tools/engagement-rate-calculator | Calculate an engagement rate |
| [**checkLinkPreview()**](FreeToolsApi.md#checkLinkPreview) | **POST** /tools/link-preview-checker | Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags) |
| [**checkPost()**](FreeToolsApi.md#checkPost) | **POST** /tools/social-media-post-checker | Check a post against each network&#39;s publishing rules |
| [**cleanText()**](FreeToolsApi.md#cleanText) | **POST** /tools/ai-text-cleaner | Clean AI-written text: dashes, quotes, invisible characters, markdown |
| [**countCharacters()**](FreeToolsApi.md#countCharacters) | **POST** /tools/social-media-character-counter | Count characters as each network counts them |
| [**formatLinkedInPost()**](FreeToolsApi.md#formatLinkedInPost) | **POST** /tools/linkedin-post-formatter | Format a LinkedIn post with bold, italic and lists |
| [**generateCaption()**](FreeToolsApi.md#generateCaption) | **POST** /tools/instagram-caption-generator | Write three post captions for a topic with AI (needs a token, spends AI credits) |
| [**generateFancyText()**](FreeToolsApi.md#generateFancyText) | **POST** /tools/fancy-text-generator | Convert text to fancy Unicode styles |
| [**generateHashtags()**](FreeToolsApi.md#generateHashtags) | **POST** /tools/instagram-hashtag-generator | Generate hashtags for a post topic with AI (needs a token, spends AI credits) |
| [**generateHooks()**](FreeToolsApi.md#generateHooks) | **POST** /tools/hook-generator | Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits) |
| [**generateQrCode()**](FreeToolsApi.md#generateQrCode) | **POST** /tools/qr-code-generator | Generate a QR code (SVG) for a link or text, with optional UTM tags |
| [**getBestTimesToPost()**](FreeToolsApi.md#getBestTimesToPost) | **GET** /tools/best-time-to-post | Get the best times to post per network from published studies, with sources |
| [**getHookTemplates()**](FreeToolsApi.md#getHookTemplates) | **GET** /tools/hook-generator/library | Get free hook templates for social media posts, filtered by style and network |
| [**getImageSizes()**](FreeToolsApi.md#getImageSizes) | **GET** /tools/social-media-image-sizes | Get social media image sizes per network, each with its source |
| [**listFreeTools()**](FreeToolsApi.md#listFreeTools) | **GET** /tools | List the free tools |
| [**previewPost()**](FreeToolsApi.md#previewPost) | **POST** /tools/social-media-post-preview | Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook |
| [**splitThread()**](FreeToolsApi.md#splitThread) | **POST** /tools/x-thread-maker | Split long text into a thread |


## `buildUtmUrl()`

```php
buildUtmUrl($free_tool_build_utm_url_request): \PostBoostClient\Model\FreeToolBuildUtmUrlResponse
```

Build a UTM-tagged campaign URL

Build a UTM-tagged campaign URL. The same logic as the free web tool at https://postboost.co/tools/utm-builder. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_build_utm_url_request = {"url":"https://postboost.co/pricing?plan=pro#faq","utm_source":"linkedin","utm_medium":"social","utm_campaign":"q4 launch"}; // \PostBoostClient\Model\FreeToolBuildUtmUrlRequest

try {
    $result = $apiInstance->buildUtmUrl($free_tool_build_utm_url_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->buildUtmUrl: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_build_utm_url_request** | [**\PostBoostClient\Model\FreeToolBuildUtmUrlRequest**](../Model/FreeToolBuildUtmUrlRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolBuildUtmUrlResponse**](../Model/FreeToolBuildUtmUrlResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `calculateAspectRatio()`

```php
calculateAspectRatio($free_tool_calculate_aspect_ratio_request): \PostBoostClient\Model\FreeToolCalculateAspectRatioResponse
```

Calculate an aspect ratio, or the missing side of an image at a given ratio

Calculate an aspect ratio, or the missing side of an image at a given ratio. The same logic as the free web tool at https://postboost.co/tools/aspect-ratio-calculator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_calculate_aspect_ratio_request = {"width":1080,"height":1350}; // \PostBoostClient\Model\FreeToolCalculateAspectRatioRequest

try {
    $result = $apiInstance->calculateAspectRatio($free_tool_calculate_aspect_ratio_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->calculateAspectRatio: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_calculate_aspect_ratio_request** | [**\PostBoostClient\Model\FreeToolCalculateAspectRatioRequest**](../Model/FreeToolCalculateAspectRatioRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCalculateAspectRatioResponse**](../Model/FreeToolCalculateAspectRatioResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `calculateCrop()`

```php
calculateCrop($free_tool_calculate_crop_request): \PostBoostClient\Model\FreeToolCalculateCropResponse
```

Calculate the crop box that fits an image to a social media size

Calculate the crop box that fits an image to a social media size. The same logic as the free web tool at https://postboost.co/tools/social-media-image-sizes. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_calculate_crop_request = {"width":4000,"height":3000,"network":"instagram","format":"feed-square"}; // \PostBoostClient\Model\FreeToolCalculateCropRequest

try {
    $result = $apiInstance->calculateCrop($free_tool_calculate_crop_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->calculateCrop: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_calculate_crop_request** | [**\PostBoostClient\Model\FreeToolCalculateCropRequest**](../Model/FreeToolCalculateCropRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCalculateCropResponse**](../Model/FreeToolCalculateCropResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `calculateEngagementRate()`

```php
calculateEngagementRate($free_tool_calculate_engagement_rate_request): \PostBoostClient\Model\FreeToolCalculateEngagementRateResponse
```

Calculate an engagement rate

Calculate an engagement rate. The same logic as the free web tool at https://postboost.co/tools/engagement-rate-calculator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_calculate_engagement_rate_request = {"likes":120,"comments":30,"shares":10,"base":4000,"posts":2}; // \PostBoostClient\Model\FreeToolCalculateEngagementRateRequest

try {
    $result = $apiInstance->calculateEngagementRate($free_tool_calculate_engagement_rate_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->calculateEngagementRate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_calculate_engagement_rate_request** | [**\PostBoostClient\Model\FreeToolCalculateEngagementRateRequest**](../Model/FreeToolCalculateEngagementRateRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCalculateEngagementRateResponse**](../Model/FreeToolCalculateEngagementRateResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `checkLinkPreview()`

```php
checkLinkPreview($free_tool_check_link_preview_request): \PostBoostClient\Model\FreeToolCheckLinkPreviewResponse
```

Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags)

Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags). The same logic as the free web tool at https://postboost.co/tools/link-preview-checker. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_check_link_preview_request = {"url":"https://example.com/features"}; // \PostBoostClient\Model\FreeToolCheckLinkPreviewRequest

try {
    $result = $apiInstance->checkLinkPreview($free_tool_check_link_preview_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->checkLinkPreview: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_check_link_preview_request** | [**\PostBoostClient\Model\FreeToolCheckLinkPreviewRequest**](../Model/FreeToolCheckLinkPreviewRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCheckLinkPreviewResponse**](../Model/FreeToolCheckLinkPreviewResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `checkPost()`

```php
checkPost($free_tool_check_post_request): \PostBoostClient\Model\FreeToolCheckPostResponse
```

Check a post against each network's publishing rules

Check a post against each network's publishing rules. The same logic as the free web tool at https://postboost.co/tools/social-media-post-checker. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_check_post_request = {"text":"Big news: https://postboost.co #launch","networks":["x","instagram"]}; // \PostBoostClient\Model\FreeToolCheckPostRequest

try {
    $result = $apiInstance->checkPost($free_tool_check_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->checkPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_check_post_request** | [**\PostBoostClient\Model\FreeToolCheckPostRequest**](../Model/FreeToolCheckPostRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCheckPostResponse**](../Model/FreeToolCheckPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `cleanText()`

```php
cleanText($free_tool_clean_text_request): \PostBoostClient\Model\FreeToolCleanTextResponse
```

Clean AI-written text: dashes, quotes, invisible characters, markdown

Clean AI-written text: dashes, quotes, invisible characters, markdown. The same logic as the free web tool at https://postboost.co/tools/ai-text-cleaner. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_clean_text_request = {"text":"Fast — reliable… and “simple”."}; // \PostBoostClient\Model\FreeToolCleanTextRequest

try {
    $result = $apiInstance->cleanText($free_tool_clean_text_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->cleanText: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_clean_text_request** | [**\PostBoostClient\Model\FreeToolCleanTextRequest**](../Model/FreeToolCleanTextRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCleanTextResponse**](../Model/FreeToolCleanTextResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `countCharacters()`

```php
countCharacters($free_tool_count_characters_request): \PostBoostClient\Model\FreeToolCountCharactersResponse
```

Count characters as each network counts them

Count characters as each network counts them. The same logic as the free web tool at https://postboost.co/tools/social-media-character-counter. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_count_characters_request = {"text":"New post: https://postboost.co/tools","network":"x"}; // \PostBoostClient\Model\FreeToolCountCharactersRequest

try {
    $result = $apiInstance->countCharacters($free_tool_count_characters_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->countCharacters: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_count_characters_request** | [**\PostBoostClient\Model\FreeToolCountCharactersRequest**](../Model/FreeToolCountCharactersRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCountCharactersResponse**](../Model/FreeToolCountCharactersResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `formatLinkedInPost()`

```php
formatLinkedInPost($free_tool_format_linked_in_post_request): \PostBoostClient\Model\FreeToolFormatLinkedInPostResponse
```

Format a LinkedIn post with bold, italic and lists

Format a LinkedIn post with bold, italic and lists. The same logic as the free web tool at https://postboost.co/tools/linkedin-post-formatter. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_format_linked_in_post_request = {"text":"Three tips\nPlan ahead\nReuse posts","list":"numbered"}; // \PostBoostClient\Model\FreeToolFormatLinkedInPostRequest

try {
    $result = $apiInstance->formatLinkedInPost($free_tool_format_linked_in_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->formatLinkedInPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_format_linked_in_post_request** | [**\PostBoostClient\Model\FreeToolFormatLinkedInPostRequest**](../Model/FreeToolFormatLinkedInPostRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolFormatLinkedInPostResponse**](../Model/FreeToolFormatLinkedInPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateCaption()`

```php
generateCaption($free_tool_generate_caption_request): \PostBoostClient\Model\FreeToolGenerateCaptionResponse
```

Write three post captions for a topic with AI (needs a token, spends AI credits)

Write three post captions for a topic with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/instagram-caption-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$free_tool_generate_caption_request = {"text":"Weekend sale on all candles","network":"instagram","tone":"playful","hashtags":true}; // \PostBoostClient\Model\FreeToolGenerateCaptionRequest

try {
    $result = $apiInstance->generateCaption($free_tool_generate_caption_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateCaption: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_caption_request** | [**\PostBoostClient\Model\FreeToolGenerateCaptionRequest**](../Model/FreeToolGenerateCaptionRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateCaptionResponse**](../Model/FreeToolGenerateCaptionResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateFancyText()`

```php
generateFancyText($free_tool_generate_fancy_text_request): \PostBoostClient\Model\FreeToolGenerateFancyTextResponse
```

Convert text to fancy Unicode styles

Convert text to fancy Unicode styles. The same logic as the free web tool at https://postboost.co/tools/fancy-text-generator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_generate_fancy_text_request = {"text":"Hello 123","style":"bold"}; // \PostBoostClient\Model\FreeToolGenerateFancyTextRequest

try {
    $result = $apiInstance->generateFancyText($free_tool_generate_fancy_text_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateFancyText: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_fancy_text_request** | [**\PostBoostClient\Model\FreeToolGenerateFancyTextRequest**](../Model/FreeToolGenerateFancyTextRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateFancyTextResponse**](../Model/FreeToolGenerateFancyTextResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateHashtags()`

```php
generateHashtags($free_tool_generate_hashtags_request): \PostBoostClient\Model\FreeToolGenerateHashtagsResponse
```

Generate hashtags for a post topic with AI (needs a token, spends AI credits)

Generate hashtags for a post topic with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/instagram-hashtag-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$free_tool_generate_hashtags_request = {"topic":"Morning routine for busy founders","network":"instagram"}; // \PostBoostClient\Model\FreeToolGenerateHashtagsRequest

try {
    $result = $apiInstance->generateHashtags($free_tool_generate_hashtags_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateHashtags: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_hashtags_request** | [**\PostBoostClient\Model\FreeToolGenerateHashtagsRequest**](../Model/FreeToolGenerateHashtagsRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateHashtagsResponse**](../Model/FreeToolGenerateHashtagsResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateHooks()`

```php
generateHooks($free_tool_generate_hooks_request): \PostBoostClient\Model\FreeToolGenerateHooksResponse
```

Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits)

Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/hook-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$free_tool_generate_hooks_request = {"topic":"Email newsletters for a small bakery","network":"instagram","count":2}; // \PostBoostClient\Model\FreeToolGenerateHooksRequest

try {
    $result = $apiInstance->generateHooks($free_tool_generate_hooks_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateHooks: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_hooks_request** | [**\PostBoostClient\Model\FreeToolGenerateHooksRequest**](../Model/FreeToolGenerateHooksRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateHooksResponse**](../Model/FreeToolGenerateHooksResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateQrCode()`

```php
generateQrCode($free_tool_generate_qr_code_request): \PostBoostClient\Model\FreeToolGenerateQrCodeResponse
```

Generate a QR code (SVG) for a link or text, with optional UTM tags

Generate a QR code (SVG) for a link or text, with optional UTM tags. The same logic as the free web tool at https://postboost.co/tools/qr-code-generator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_generate_qr_code_request = {"data":"https://postboost.co","utm":{"source":"flyer"},"size":128}; // \PostBoostClient\Model\FreeToolGenerateQrCodeRequest

try {
    $result = $apiInstance->generateQrCode($free_tool_generate_qr_code_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateQrCode: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_qr_code_request** | [**\PostBoostClient\Model\FreeToolGenerateQrCodeRequest**](../Model/FreeToolGenerateQrCodeRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateQrCodeResponse**](../Model/FreeToolGenerateQrCodeResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBestTimesToPost()`

```php
getBestTimesToPost($network): \PostBoostClient\Model\FreeToolGetBestTimesToPostResponse
```

Get the best times to post per network from published studies, with sources

Get the best times to post per network from published studies, with sources. The same logic as the free web tool at https://postboost.co/tools/best-time-to-post. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$network = 'network_example'; // string

try {
    $result = $apiInstance->getBestTimesToPost($network);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->getBestTimesToPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **network** | **string**|  | [optional] |

### Return type

[**\PostBoostClient\Model\FreeToolGetBestTimesToPostResponse**](../Model/FreeToolGetBestTimesToPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getHookTemplates()`

```php
getHookTemplates($topic, $category, $network, $search): \PostBoostClient\Model\FreeToolGetHookTemplatesResponse
```

Get free hook templates for social media posts, filtered by style and network

Get free hook templates for social media posts, filtered by style and network. The same logic as the free web tool at https://postboost.co/tools/hook-generator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$topic = 'topic_example'; // string
$category = 'category_example'; // string
$network = 'network_example'; // string
$search = 'search_example'; // string

try {
    $result = $apiInstance->getHookTemplates($topic, $category, $network, $search);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->getHookTemplates: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **topic** | **string**|  | [optional] |
| **category** | **string**|  | [optional] |
| **network** | **string**|  | [optional] |
| **search** | **string**|  | [optional] |

### Return type

[**\PostBoostClient\Model\FreeToolGetHookTemplatesResponse**](../Model/FreeToolGetHookTemplatesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getImageSizes()`

```php
getImageSizes($network): \PostBoostClient\Model\FreeToolGetImageSizesResponse
```

Get social media image sizes per network, each with its source

Get social media image sizes per network, each with its source. The same logic as the free web tool at https://postboost.co/tools/social-media-image-sizes. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$network = 'network_example'; // string

try {
    $result = $apiInstance->getImageSizes($network);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->getImageSizes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **network** | **string**|  | [optional] |

### Return type

[**\PostBoostClient\Model\FreeToolGetImageSizesResponse**](../Model/FreeToolGetImageSizesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listFreeTools()`

```php
listFreeTools(): \PostBoostClient\Model\FreeToolList
```

List the free tools

Every free tool the API serves, with its operationId and web page. No token needed.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

try {
    $result = $apiInstance->listFreeTools();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->listFreeTools: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

[**\PostBoostClient\Model\FreeToolList**](../Model/FreeToolList.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `previewPost()`

```php
previewPost($free_tool_preview_post_request): \PostBoostClient\Model\FreeToolPreviewPostResponse
```

Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook

Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook. The same logic as the free web tool at https://postboost.co/tools/social-media-post-preview. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_preview_post_request = {"text":"New feature: schedule a month of posts in one sitting."}; // \PostBoostClient\Model\FreeToolPreviewPostRequest

try {
    $result = $apiInstance->previewPost($free_tool_preview_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->previewPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_preview_post_request** | [**\PostBoostClient\Model\FreeToolPreviewPostRequest**](../Model/FreeToolPreviewPostRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolPreviewPostResponse**](../Model/FreeToolPreviewPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `splitThread()`

```php
splitThread($free_tool_split_thread_request): \PostBoostClient\Model\FreeToolSplitThreadResponse
```

Split long text into a thread

Split long text into a thread. The same logic as the free web tool at https://postboost.co/tools/x-thread-maker. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_split_thread_request = {"text":"Short one.\n\nShort two.\n---\nSecond post.","numbering":true}; // \PostBoostClient\Model\FreeToolSplitThreadRequest

try {
    $result = $apiInstance->splitThread($free_tool_split_thread_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->splitThread: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_split_thread_request** | [**\PostBoostClient\Model\FreeToolSplitThreadRequest**](../Model/FreeToolSplitThreadRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolSplitThreadResponse**](../Model/FreeToolSplitThreadResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
