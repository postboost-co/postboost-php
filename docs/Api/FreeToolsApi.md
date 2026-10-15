# PostBoostClient\FreeToolsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**buildUtmUrl()**](FreeToolsApi.md#buildUtmUrl) | **POST** /tools/utm-builder | Build a UTM-tagged campaign URL |
| [**calculateEngagementRate()**](FreeToolsApi.md#calculateEngagementRate) | **POST** /tools/engagement-rate-calculator | Calculate an engagement rate |
| [**cleanText()**](FreeToolsApi.md#cleanText) | **POST** /tools/ai-text-cleaner | Clean AI-written text: dashes, quotes, invisible characters, markdown |
| [**countCharacters()**](FreeToolsApi.md#countCharacters) | **POST** /tools/social-media-character-counter | Count characters as each network counts them |
| [**formatLinkedInPost()**](FreeToolsApi.md#formatLinkedInPost) | **POST** /tools/linkedin-post-formatter | Format a LinkedIn post with bold, italic and lists |
| [**generateFancyText()**](FreeToolsApi.md#generateFancyText) | **POST** /tools/fancy-text-generator | Convert text to fancy Unicode styles |
| [**listFreeTools()**](FreeToolsApi.md#listFreeTools) | **GET** /tools | List the free tools |
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
