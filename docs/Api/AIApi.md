# PostBoostClient\AIApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**blogToSocial()**](AIApi.md#blogToSocial) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post |
| [**deleteBrandVoice()**](AIApi.md#deleteBrandVoice) | **DELETE** /{workspaceUuid}/brand-voice | Delete the brand voice |
| [**getAIUsage()**](AIApi.md#getAIUsage) | **GET** /{workspaceUuid}/usage/ai | AI credit usage |
| [**getBrandVoice()**](AIApi.md#getBrandVoice) | **GET** /{workspaceUuid}/brand-voice | Get the brand voice |
| [**getRepurposeRun()**](AIApi.md#getRepurposeRun) | **GET** /{workspaceUuid}/ai/repurpose/runs/{runId} | Get a repurpose run |
| [**imageAltText()**](AIApi.md#imageAltText) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI |
| [**imageEdit()**](AIApi.md#imageEdit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI |
| [**imageGenerate()**](AIApi.md#imageGenerate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption |
| [**imagePrompt()**](AIApi.md#imagePrompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption |
| [**imageVariations()**](AIApi.md#imageVariations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image |
| [**learnBrandVoice()**](AIApi.md#learnBrandVoice) | **POST** /{workspaceUuid}/brand-voice/learn | Learn a brand voice from past posts |
| [**repurposeContent()**](AIApi.md#repurposeContent) | **POST** /{workspaceUuid}/ai/repurpose | Repurpose long-form content into a draft post set with a carousel |
| [**updateBrandVoice()**](AIApi.md#updateBrandVoice) | **PUT** /{workspaceUuid}/brand-voice | Create or update the brand voice |


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

## `deleteBrandVoice()`

```php
deleteBrandVoice($workspace_uuid): object
```

Delete the brand voice

Removes the workspace's brand voice. AI endpoints then run without one. Admins and members only.

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

try {
    $result = $apiInstance->deleteBrandVoice($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->deleteBrandVoice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

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

## `getAIUsage()`

```php
getAIUsage($workspace_uuid): \PostBoostClient\Model\AIUsage
```

AI credit usage

The workspace's AI credits: text credits (captions, rewrites, outlines, alt text; counted per billing cycle) and image credits (one per generated, edited or varied image, and one per repurpose carousel; counted per calendar month, UTC). `limit` and `remaining` are `null` when the workspace has no limit. Readable when credits are used up; costs nothing.  When image credits run out, the image endpoints and carousels answer `429` with `code: image_credits_exhausted`; when text credits run out, the AI endpoints answer `429` with `code: ai_credits_exhausted`. Image endpoint responses also carry `image_credits_used` and `image_credits_remaining`; their `credits_used` counts text credits only. If the image pool is switched off (`image.enabled: false`), images cost text credits as before.

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

try {
    $result = $apiInstance->getAIUsage($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->getAIUsage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\AIUsage**](../Model/AIUsage.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getBrandVoice()`

```php
getBrandVoice($workspace_uuid): \PostBoostClient\Model\GetBrandVoice200Response
```

Get the brand voice

The workspace's brand voice: identity, audience, tone sliders, style rules and example posts. It is the same profile as the Brand Voice page in the app (one per workspace). `data` is `null` when no voice is set. Any workspace member may read it; reading costs no AI credits.  The AI endpoints apply it automatically: `blog-to-social` adds it to the caption instructions, `image-prompt` and `image-generate` turn it into a short visual tone line, and `image-edit` applies it when you send `use_brand_voice: true`. `image-variations` and `image-alt-text` never use it (alt text must describe the image literally). Send `use_brand_voice: false` to skip it on a call; responses report `meta.brand_voice_applied`.

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

try {
    $result = $apiInstance->getBrandVoice($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->getBrandVoice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\GetBrandVoice200Response**](../Model/GetBrandVoice200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getRepurposeRun()`

```php
getRepurposeRun($workspace_uuid, $run_id): \PostBoostClient\Model\GetRepurposeRun200Response
```

Get a repurpose run

Status of a run started by `repurposeContent`. `queued` and `running` mean it is still going; poll again in a few seconds. A run that has not finished after 10 minutes reports `failed`. `result` holds the same `data` body a `200` from `repurposeContent` returns, for one hour after the run ended with `ok` or `partial`; after that it is `null` (the draft post stays). Limited to 60 calls per minute.

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
$run_id = 56; // int | The `run_id` from `repurposeContent`.

try {
    $result = $apiInstance->getRepurposeRun($workspace_uuid, $run_id);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->getRepurposeRun: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **run_id** | **int**| The &#x60;run_id&#x60; from &#x60;repurposeContent&#x60;. | |

### Return type

[**\PostBoostClient\Model\GetRepurposeRun200Response**](../Model/GetRepurposeRun200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
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

## `learnBrandVoice()`

```php
learnBrandVoice($workspace_uuid, $learn_brand_voice_input): \PostBoostClient\Model\LearnBrandVoiceResponse
```

Learn a brand voice from past posts

Reads the workspace's latest published posts (original text) and proposes a brand voice in the same shape as `GET /brand-voice`. Returns a draft and saves nothing unless `apply: true`.  Without `overwrite`, learned values only fill fields that are empty (tone sliders and styles still at their defaults count as empty); with `overwrite: true` they replace them. The first five sampled posts become `example_posts`. Needs at least 3 published posts (`422`, `code: not_enough_posts`). Costs one AI text credit per AI call (one retry when the reply is not usable). Admins and members only. A key limited to some accounts must send `account_ids`; only posts whose accounts are all among them are read. `apply` also needs the `write` ability.

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
$learn_brand_voice_input = new \PostBoostClient\Model\LearnBrandVoiceInput(); // \PostBoostClient\Model\LearnBrandVoiceInput

try {
    $result = $apiInstance->learnBrandVoice($workspace_uuid, $learn_brand_voice_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->learnBrandVoice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **learn_brand_voice_input** | [**\PostBoostClient\Model\LearnBrandVoiceInput**](../Model/LearnBrandVoiceInput.md)|  | [optional] |

### Return type

[**\PostBoostClient\Model\LearnBrandVoiceResponse**](../Model/LearnBrandVoiceResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `repurposeContent()`

```php
repurposeContent($workspace_uuid, $repurpose_input, $idempotency_key): \PostBoostClient\Model\RepurposeContent200Response
```

Repurpose long-form content into a draft post set with a carousel

Turns an article URL, a YouTube video, a PDF or pasted text into one **draft** post with a caption for every target account, plus a carousel of rendered slide images (hook, 1 to 6 idea slides, call to action; 1080×1350 PNG). Nothing is published or scheduled.  **Sources** (`source_type`): - `url`: the article is fetched and its main text extracted. - `youtube`: title, description and chapters come from YouTube; send the transcript in   `transcript` for better results (required when the description is short). - `pdf`: `pdf_url` must be a public PDF of at most 20 MB; the first 30 pages are read. - `text`: send `title` and `text`.  **Carousel per network**: Instagram, Facebook, Threads up to 10 slides; LinkedIn up to 9; X and Bluesky up to 4; other networks get the cover slide; YouTube and TikTok get none (listed in `warnings`). Without a carousel, the source image (article image or video thumbnail) is attached when available.  **AI credits**: one per target account plus one for the carousel outline. Slides are drawn without AI and cost nothing. The workspace brand voice applies unless `use_brand_voice` is `false`. Send an `Idempotency-Key` so a retried call does not create a second draft. Limited to 10 calls per minute.  **Long runs**: the run is queued. The call waits up to 20 seconds and answers `200` with the result when the run finished by then. Otherwise it answers `202` with a `run_id`; poll `getRepurposeRun` (`status_url`) every few seconds until the status is `ok`, `partial` or `failed`. Send `async: true` to get the `202` right away. Validation, account and credit errors are answered before anything is queued.

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
$repurpose_input = {"source_type":"url","url":"https://example.com/blog/my-post","platforms":["instagram","linkedin_page"],"slide_count":7}; // \PostBoostClient\Model\RepurposeInput
$idempotency_key = 'idempotency_key_example'; // string | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.

try {
    $result = $apiInstance->repurposeContent($workspace_uuid, $repurpose_input, $idempotency_key);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->repurposeContent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **repurpose_input** | [**\PostBoostClient\Model\RepurposeInput**](../Model/RepurposeInput.md)|  | |
| **idempotency_key** | **string**| Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with &#x60;Idempotent-Replayed: true&#x60; and has no further effect. Keys are scoped to your user, the workspace, the method and the path. | [optional] |

### Return type

[**\PostBoostClient\Model\RepurposeContent200Response**](../Model/RepurposeContent200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateBrandVoice()`

```php
updateBrandVoice($workspace_uuid, $brand_voice_input): \PostBoostClient\Model\GetBrandVoice200Response
```

Create or update the brand voice

Creates the workspace's brand voice or updates it. Fields you leave out keep their current value. Admins and members only (not viewers); the workspace must have AI enabled.

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
$brand_voice_input = {"business_name":"Northwind Coffee","industry":"Specialty coffee roasting","personality":"Warm and curious about every bean. Never pushy.","audience":["home baristas","cafe owners"],"tone_formal":2,"tone_playful":4,"tone_technical":3,"emoji_style":"rare","hashtag_strategy":"branded","avoid_words":["cheap","best ever"]}; // \PostBoostClient\Model\BrandVoiceInput

try {
    $result = $apiInstance->updateBrandVoice($workspace_uuid, $brand_voice_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AIApi->updateBrandVoice: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **brand_voice_input** | [**\PostBoostClient\Model\BrandVoiceInput**](../Model/BrandVoiceInput.md)|  | |

### Return type

[**\PostBoostClient\Model\GetBrandVoice200Response**](../Model/GetBrandVoice200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
