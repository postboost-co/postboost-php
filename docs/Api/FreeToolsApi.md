# PostBoostClient\FreeToolsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**buildAgentSkill()**](FreeToolsApi.md#buildAgentSkill) | **POST** /tools/social-media-agent-skill-builder | Build a SKILL.md, AGENTS.md or system prompt for a social media agent |
| [**buildHashtagGroups()**](FreeToolsApi.md#buildHashtagGroups) | **POST** /tools/hashtag-group-builder | Clean, dedupe and split hashtags into groups that fit a network&#39;s hashtag cap |
| [**buildUtmUrl()**](FreeToolsApi.md#buildUtmUrl) | **POST** /tools/utm-builder | Build a UTM-tagged campaign URL |
| [**calculateAspectRatio()**](FreeToolsApi.md#calculateAspectRatio) | **POST** /tools/aspect-ratio-calculator | Calculate an aspect ratio, or the missing side of an image at a given ratio |
| [**calculateCarouselSlices()**](FreeToolsApi.md#calculateCarouselSlices) | **POST** /tools/instagram-carousel-splitter | Split a wide image into seamless Instagram carousel slides |
| [**calculateCrop()**](FreeToolsApi.md#calculateCrop) | **POST** /tools/social-media-image-sizes/crop | Calculate the crop box that fits an image to a social media size |
| [**calculateEngagementRate()**](FreeToolsApi.md#calculateEngagementRate) | **POST** /tools/engagement-rate-calculator | Calculate an engagement rate |
| [**calculateInfluencerRate()**](FreeToolsApi.md#calculateInfluencerRate) | **POST** /tools/influencer-rate-calculator | Estimate an influencer&#39;s rate for one sponsored deliverable |
| [**calculateSmmPricing()**](FreeToolsApi.md#calculateSmmPricing) | **POST** /tools/social-media-manager-pricing-calculator | Estimate social media manager pricing |
| [**calculateSocialRoi()**](FreeToolsApi.md#calculateSocialRoi) | **POST** /tools/social-media-roi-calculator | Calculate social media ROI |
| [**calculateXApiCost()**](FreeToolsApi.md#calculateXApiCost) | **POST** /tools/x-api-cost-calculator | Calculate the monthly X API cost |
| [**checkLinkPreview()**](FreeToolsApi.md#checkLinkPreview) | **POST** /tools/link-preview-checker | Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags) |
| [**checkPost()**](FreeToolsApi.md#checkPost) | **POST** /tools/social-media-post-checker | Check a post against each network&#39;s publishing rules |
| [**checkReadability()**](FreeToolsApi.md#checkReadability) | **POST** /tools/post-readability-checker | Check the readability of a post: Flesch scores, long sentences and passive hints |
| [**checkYoutubeThumbnail()**](FreeToolsApi.md#checkYoutubeThumbnail) | **POST** /tools/youtube-thumbnail-size-checker | Check a YouTube thumbnail&#39;s ratio, width, file size and format against YouTube&#39;s requirements |
| [**cleanText()**](FreeToolsApi.md#cleanText) | **POST** /tools/ai-text-cleaner | Clean AI-written text: dashes, quotes, invisible characters, markdown |
| [**countCharacters()**](FreeToolsApi.md#countCharacters) | **POST** /tools/social-media-character-counter | Count characters as each network counts them |
| [**findAutomationRecipes()**](FreeToolsApi.md#findAutomationRecipes) | **GET** /tools/social-media-automation-recipes | Find n8n, Zapier and Make recipes that automate social media posting through the PostBoost API |
| [**formatCrossPost()**](FreeToolsApi.md#formatCrossPost) | **POST** /tools/cross-post-formatter | Format one post for X, Threads, Bluesky, Mastodon and LinkedIn |
| [**formatInstagramCaption()**](FreeToolsApi.md#formatInstagramCaption) | **POST** /tools/instagram-line-break-generator | Keep blank lines in an Instagram caption with spacer lines, and count it |
| [**formatLinkedInPost()**](FreeToolsApi.md#formatLinkedInPost) | **POST** /tools/linkedin-post-formatter | Format a LinkedIn post with bold, italic and lists |
| [**generateAltText()**](FreeToolsApi.md#generateAltText) | **POST** /tools/alt-text-generator | Write alt text for an image with AI (needs a token, spends AI credits) |
| [**generateBio()**](FreeToolsApi.md#generateBio) | **POST** /tools/instagram-bio-generator | Write five profile bios with AI (needs a token, spends AI credits) |
| [**generateCaption()**](FreeToolsApi.md#generateCaption) | **POST** /tools/instagram-caption-generator | Write three post captions for a topic with AI (needs a token, spends AI credits) |
| [**generateFancyText()**](FreeToolsApi.md#generateFancyText) | **POST** /tools/fancy-text-generator | Convert text to fancy Unicode styles |
| [**generateHashtags()**](FreeToolsApi.md#generateHashtags) | **POST** /tools/instagram-hashtag-generator | Generate hashtags for a post topic with AI (needs a token, spends AI credits) |
| [**generateHooks()**](FreeToolsApi.md#generateHooks) | **POST** /tools/hook-generator | Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits) |
| [**generateLinkedInHeadline()**](FreeToolsApi.md#generateLinkedInHeadline) | **POST** /tools/linkedin-headline-generator | Write five LinkedIn profile headlines with AI (needs a token, spends AI credits) |
| [**generateQrCode()**](FreeToolsApi.md#generateQrCode) | **POST** /tools/qr-code-generator | Generate a QR code (SVG) for a link or text, with optional UTM tags |
| [**generateSocialPostsFromBlog()**](FreeToolsApi.md#generateSocialPostsFromBlog) | **POST** /tools/blog-to-social-media | Turn a blog post (URL or text) into one social post per network with AI (needs a token, spends AI credits) |
| [**generateUsernames()**](FreeToolsApi.md#generateUsernames) | **POST** /tools/social-media-username-generator | Generate social media usernames |
| [**generateYoutubeDescription()**](FreeToolsApi.md#generateYoutubeDescription) | **POST** /tools/youtube-description-generator | Write three YouTube video descriptions with AI (needs a token, spends AI credits) |
| [**generateYoutubeTitles()**](FreeToolsApi.md#generateYoutubeTitles) | **POST** /tools/youtube-title-generator | Write five YouTube video titles with AI (needs a token, spends AI credits) |
| [**getBestTimesToPost()**](FreeToolsApi.md#getBestTimesToPost) | **GET** /tools/best-time-to-post | Get the best times to post per network from published studies, with sources |
| [**getGlossary()**](FreeToolsApi.md#getGlossary) | **GET** /tools/social-media-glossary | Look up social media terms: plain-language definitions by category, with sources and related terms |
| [**getHookTemplates()**](FreeToolsApi.md#getHookTemplates) | **GET** /tools/hook-generator/library | Get free hook templates for social media posts, filtered by style and network |
| [**getImageSizes()**](FreeToolsApi.md#getImageSizes) | **GET** /tools/social-media-image-sizes | Get social media image sizes per network, each with its source |
| [**getSafeZones()**](FreeToolsApi.md#getSafeZones) | **POST** /tools/safe-zone-checker | Get the TikTok, Instagram Reels or YouTube Shorts safe zones for a vertical frame |
| [**getVideoSpecs()**](FreeToolsApi.md#getVideoSpecs) | **GET** /tools/social-media-video-specs | Get social media video ratios, resolutions, lengths and file size limits per network, with sources |
| [**listAwarenessDays()**](FreeToolsApi.md#listAwarenessDays) | **GET** /tools/social-media-holiday-calendar | List public holidays, awareness days and social media days by date, country, type and topic, with sources |
| [**listFreeTools()**](FreeToolsApi.md#listFreeTools) | **GET** /tools | List the free tools |
| [**pickGiveawayWinners()**](FreeToolsApi.md#pickGiveawayWinners) | **POST** /tools/giveaway-comment-picker | Pick giveaway winners with a draw anyone can verify |
| [**pickSocialMediaTool()**](FreeToolsApi.md#pickSocialMediaTool) | **POST** /tools/social-media-tool-picker | Match your needs against social media management tools and see what each one misses |
| [**planContentCalendar()**](FreeToolsApi.md#planContentCalendar) | **POST** /tools/social-media-content-calendar-generator | Plan a social media content calendar and get it as CSV and ICS |
| [**planPostingFrequency()**](FreeToolsApi.md#planPostingFrequency) | **POST** /tools/posting-frequency-planner | Plan how often to post on each network |
| [**previewPost()**](FreeToolsApi.md#previewPost) | **POST** /tools/social-media-post-preview | Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook |
| [**scoreSocialAudit()**](FreeToolsApi.md#scoreSocialAudit) | **POST** /tools/social-media-audit-template | Score a social media audit checklist and get the top fixes |
| [**searchEmoji()**](FreeToolsApi.md#searchEmoji) | **POST** /tools/social-media-emoji-picker | Search emoji by name or keyword, to copy and paste into a post |
| [**splitThread()**](FreeToolsApi.md#splitThread) | **POST** /tools/x-thread-maker | Split long text into a thread |
| [**summarizeReport()**](FreeToolsApi.md#summarizeReport) | **POST** /tools/social-media-report-generator | Summarize social media post metrics into a report |
| [**verifyWebhookSignature()**](FreeToolsApi.md#verifyWebhookSignature) | **POST** /tools/webhook-signature-verifier | Verify an HMAC webhook signature |


## `buildAgentSkill()`

```php
buildAgentSkill($free_tool_build_agent_skill_request): \PostBoostClient\Model\FreeToolBuildAgentSkillResponse
```

Build a SKILL.md, AGENTS.md or system prompt for a social media agent

Build a SKILL.md, AGENTS.md or system prompt for a social media agent. The same logic as the free web tool at https://postboost.co/tools/social-media-agent-skill-builder. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_build_agent_skill_request = {"brand":"Acme Bakery","tasks":["draft_posts"],"networks":["instagram"],"daily_cap":3}; // \PostBoostClient\Model\FreeToolBuildAgentSkillRequest

try {
    $result = $apiInstance->buildAgentSkill($free_tool_build_agent_skill_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->buildAgentSkill: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_build_agent_skill_request** | [**\PostBoostClient\Model\FreeToolBuildAgentSkillRequest**](../Model/FreeToolBuildAgentSkillRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolBuildAgentSkillResponse**](../Model/FreeToolBuildAgentSkillResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `buildHashtagGroups()`

```php
buildHashtagGroups($free_tool_build_hashtag_groups_request): \PostBoostClient\Model\FreeToolBuildHashtagGroupsResponse
```

Clean, dedupe and split hashtags into groups that fit a network's hashtag cap

Clean, dedupe and split hashtags into groups that fit a network's hashtag cap. The same logic as the free web tool at https://postboost.co/tools/hashtag-group-builder. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_build_hashtag_groups_request = {"text":"travel, #Travel  #travel_tips 2026 #photo!graphy"}; // \PostBoostClient\Model\FreeToolBuildHashtagGroupsRequest

try {
    $result = $apiInstance->buildHashtagGroups($free_tool_build_hashtag_groups_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->buildHashtagGroups: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_build_hashtag_groups_request** | [**\PostBoostClient\Model\FreeToolBuildHashtagGroupsRequest**](../Model/FreeToolBuildHashtagGroupsRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolBuildHashtagGroupsResponse**](../Model/FreeToolBuildHashtagGroupsResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

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

## `calculateCarouselSlices()`

```php
calculateCarouselSlices($free_tool_calculate_carousel_slices_request): \PostBoostClient\Model\FreeToolCalculateCarouselSlicesResponse
```

Split a wide image into seamless Instagram carousel slides

Split a wide image into seamless Instagram carousel slides. The same logic as the free web tool at https://postboost.co/tools/instagram-carousel-splitter. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_calculate_carousel_slices_request = {"width":3240,"height":1350,"slides":3,"ratio":"4:5"}; // \PostBoostClient\Model\FreeToolCalculateCarouselSlicesRequest

try {
    $result = $apiInstance->calculateCarouselSlices($free_tool_calculate_carousel_slices_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->calculateCarouselSlices: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_calculate_carousel_slices_request** | [**\PostBoostClient\Model\FreeToolCalculateCarouselSlicesRequest**](../Model/FreeToolCalculateCarouselSlicesRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCalculateCarouselSlicesResponse**](../Model/FreeToolCalculateCarouselSlicesResponse.md)

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

## `calculateInfluencerRate()`

```php
calculateInfluencerRate($free_tool_calculate_influencer_rate_request): \PostBoostClient\Model\FreeToolCalculateInfluencerRateResponse
```

Estimate an influencer's rate for one sponsored deliverable

Estimate an influencer's rate for one sponsored deliverable. The same logic as the free web tool at https://postboost.co/tools/influencer-rate-calculator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_calculate_influencer_rate_request = {"network":"instagram","followers":25000,"deliverable":"reel","usage_rights_months":3}; // \PostBoostClient\Model\FreeToolCalculateInfluencerRateRequest

try {
    $result = $apiInstance->calculateInfluencerRate($free_tool_calculate_influencer_rate_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->calculateInfluencerRate: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_calculate_influencer_rate_request** | [**\PostBoostClient\Model\FreeToolCalculateInfluencerRateRequest**](../Model/FreeToolCalculateInfluencerRateRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCalculateInfluencerRateResponse**](../Model/FreeToolCalculateInfluencerRateResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `calculateSmmPricing()`

```php
calculateSmmPricing($free_tool_calculate_smm_pricing_request): \PostBoostClient\Model\FreeToolCalculateSmmPricingResponse
```

Estimate social media manager pricing

Estimate social media manager pricing. The same logic as the free web tool at https://postboost.co/tools/social-media-manager-pricing-calculator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_calculate_smm_pricing_request = {"networks":3,"posts_per_week":5,"content_type":"copy_design","community_hours_per_week":4,"hourly_rate":50}; // \PostBoostClient\Model\FreeToolCalculateSmmPricingRequest

try {
    $result = $apiInstance->calculateSmmPricing($free_tool_calculate_smm_pricing_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->calculateSmmPricing: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_calculate_smm_pricing_request** | [**\PostBoostClient\Model\FreeToolCalculateSmmPricingRequest**](../Model/FreeToolCalculateSmmPricingRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCalculateSmmPricingResponse**](../Model/FreeToolCalculateSmmPricingResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `calculateSocialRoi()`

```php
calculateSocialRoi($free_tool_calculate_social_roi_request): \PostBoostClient\Model\FreeToolCalculateSocialRoiResponse
```

Calculate social media ROI

Calculate social media ROI. The same logic as the free web tool at https://postboost.co/tools/social-media-roi-calculator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_calculate_social_roi_request = {"revenue":5000,"costs":{"ad_spend":1000,"labor_hours":10,"hourly_rate":50}}; // \PostBoostClient\Model\FreeToolCalculateSocialRoiRequest

try {
    $result = $apiInstance->calculateSocialRoi($free_tool_calculate_social_roi_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->calculateSocialRoi: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_calculate_social_roi_request** | [**\PostBoostClient\Model\FreeToolCalculateSocialRoiRequest**](../Model/FreeToolCalculateSocialRoiRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCalculateSocialRoiResponse**](../Model/FreeToolCalculateSocialRoiResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `calculateXApiCost()`

```php
calculateXApiCost($free_tool_calculate_x_api_cost_request): \PostBoostClient\Model\FreeToolCalculateXApiCostResponse
```

Calculate the monthly X API cost

Calculate the monthly X API cost. The same logic as the free web tool at https://postboost.co/tools/x-api-cost-calculator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_calculate_x_api_cost_request = {"posts":1000,"link_share":20}; // \PostBoostClient\Model\FreeToolCalculateXApiCostRequest

try {
    $result = $apiInstance->calculateXApiCost($free_tool_calculate_x_api_cost_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->calculateXApiCost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_calculate_x_api_cost_request** | [**\PostBoostClient\Model\FreeToolCalculateXApiCostRequest**](../Model/FreeToolCalculateXApiCostRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCalculateXApiCostResponse**](../Model/FreeToolCalculateXApiCostResponse.md)

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

## `checkReadability()`

```php
checkReadability($free_tool_check_readability_request): \PostBoostClient\Model\FreeToolCheckReadabilityResponse
```

Check the readability of a post: Flesch scores, long sentences and passive hints

Check the readability of a post: Flesch scores, long sentences and passive hints. The same logic as the free web tool at https://postboost.co/tools/post-readability-checker. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_check_readability_request = {"text":"The cat sat on the mat. 🐱 #cats"}; // \PostBoostClient\Model\FreeToolCheckReadabilityRequest

try {
    $result = $apiInstance->checkReadability($free_tool_check_readability_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->checkReadability: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_check_readability_request** | [**\PostBoostClient\Model\FreeToolCheckReadabilityRequest**](../Model/FreeToolCheckReadabilityRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCheckReadabilityResponse**](../Model/FreeToolCheckReadabilityResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `checkYoutubeThumbnail()`

```php
checkYoutubeThumbnail($free_tool_check_youtube_thumbnail_request): \PostBoostClient\Model\FreeToolCheckYoutubeThumbnailResponse
```

Check a YouTube thumbnail's ratio, width, file size and format against YouTube's requirements

Check a YouTube thumbnail's ratio, width, file size and format against YouTube's requirements. The same logic as the free web tool at https://postboost.co/tools/youtube-thumbnail-size-checker. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_check_youtube_thumbnail_request = {"width":1280,"height":720,"file_size_bytes":921600,"format":"image/png"}; // \PostBoostClient\Model\FreeToolCheckYoutubeThumbnailRequest

try {
    $result = $apiInstance->checkYoutubeThumbnail($free_tool_check_youtube_thumbnail_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->checkYoutubeThumbnail: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_check_youtube_thumbnail_request** | [**\PostBoostClient\Model\FreeToolCheckYoutubeThumbnailRequest**](../Model/FreeToolCheckYoutubeThumbnailRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolCheckYoutubeThumbnailResponse**](../Model/FreeToolCheckYoutubeThumbnailResponse.md)

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

## `findAutomationRecipes()`

```php
findAutomationRecipes($platform, $trigger, $q): \PostBoostClient\Model\FreeToolFindAutomationRecipesResponse
```

Find n8n, Zapier and Make recipes that automate social media posting through the PostBoost API

Find n8n, Zapier and Make recipes that automate social media posting through the PostBoost API. The same logic as the free web tool at https://postboost.co/tools/social-media-automation-recipes. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$platform = 'platform_example'; // string
$trigger = 'trigger_example'; // string
$q = 'q_example'; // string

try {
    $result = $apiInstance->findAutomationRecipes($platform, $trigger, $q);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->findAutomationRecipes: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **platform** | **string**|  | [optional] |
| **trigger** | **string**|  | [optional] |
| **q** | **string**|  | [optional] |

### Return type

[**\PostBoostClient\Model\FreeToolFindAutomationRecipesResponse**](../Model/FreeToolFindAutomationRecipesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `formatCrossPost()`

```php
formatCrossPost($free_tool_format_cross_post_request): \PostBoostClient\Model\FreeToolFormatCrossPostResponse
```

Format one post for X, Threads, Bluesky, Mastodon and LinkedIn

Format one post for X, Threads, Bluesky, Mastodon and LinkedIn. The same logic as the free web tool at https://postboost.co/tools/cross-post-formatter. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_format_cross_post_request = {"text":"Our spring menu is live, thanks @alice for the photos: https://example.com/menu","networks":["x","mastodon","linkedin"]}; // \PostBoostClient\Model\FreeToolFormatCrossPostRequest

try {
    $result = $apiInstance->formatCrossPost($free_tool_format_cross_post_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->formatCrossPost: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_format_cross_post_request** | [**\PostBoostClient\Model\FreeToolFormatCrossPostRequest**](../Model/FreeToolFormatCrossPostRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolFormatCrossPostResponse**](../Model/FreeToolFormatCrossPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `formatInstagramCaption()`

```php
formatInstagramCaption($free_tool_format_instagram_caption_request): \PostBoostClient\Model\FreeToolFormatInstagramCaptionResponse
```

Keep blank lines in an Instagram caption with spacer lines, and count it

Keep blank lines in an Instagram caption with spacer lines, and count it. The same logic as the free web tool at https://postboost.co/tools/instagram-line-break-generator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_format_instagram_caption_request = {"text":"Line one\n\n\nLine two  "}; // \PostBoostClient\Model\FreeToolFormatInstagramCaptionRequest

try {
    $result = $apiInstance->formatInstagramCaption($free_tool_format_instagram_caption_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->formatInstagramCaption: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_format_instagram_caption_request** | [**\PostBoostClient\Model\FreeToolFormatInstagramCaptionRequest**](../Model/FreeToolFormatInstagramCaptionRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolFormatInstagramCaptionResponse**](../Model/FreeToolFormatInstagramCaptionResponse.md)

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

## `generateAltText()`

```php
generateAltText($free_tool_generate_alt_text_request): \PostBoostClient\Model\FreeToolGenerateAltTextResponse
```

Write alt text for an image with AI (needs a token, spends AI credits)

Write alt text for an image with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/alt-text-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

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
$free_tool_generate_alt_text_request = {"image_url":"https://example.com/images/sourdough.jpg","context":"our bakery opens on Saturday","length":"short"}; // \PostBoostClient\Model\FreeToolGenerateAltTextRequest

try {
    $result = $apiInstance->generateAltText($free_tool_generate_alt_text_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateAltText: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_alt_text_request** | [**\PostBoostClient\Model\FreeToolGenerateAltTextRequest**](../Model/FreeToolGenerateAltTextRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateAltTextResponse**](../Model/FreeToolGenerateAltTextResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`, `multipart/form-data`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateBio()`

```php
generateBio($free_tool_generate_bio_request): \PostBoostClient\Model\FreeToolGenerateBioResponse
```

Write five profile bios with AI (needs a token, spends AI credits)

Write five profile bios with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/instagram-bio-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

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
$free_tool_generate_bio_request = {"text":"Wedding photographer for small weddings in Lisbon","tone":"friendly"}; // \PostBoostClient\Model\FreeToolGenerateBioRequest

try {
    $result = $apiInstance->generateBio($free_tool_generate_bio_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateBio: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_bio_request** | [**\PostBoostClient\Model\FreeToolGenerateBioRequest**](../Model/FreeToolGenerateBioRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateBioResponse**](../Model/FreeToolGenerateBioResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

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

## `generateLinkedInHeadline()`

```php
generateLinkedInHeadline($free_tool_generate_linked_in_headline_request): \PostBoostClient\Model\FreeToolGenerateLinkedInHeadlineResponse
```

Write five LinkedIn profile headlines with AI (needs a token, spends AI credits)

Write five LinkedIn profile headlines with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/linkedin-headline-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

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
$free_tool_generate_linked_in_headline_request = {"role":"Customer success lead","skills":"B2B SaaS onboarding, churn analysis, customer training","audience":"SaaS founders"}; // \PostBoostClient\Model\FreeToolGenerateLinkedInHeadlineRequest

try {
    $result = $apiInstance->generateLinkedInHeadline($free_tool_generate_linked_in_headline_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateLinkedInHeadline: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_linked_in_headline_request** | [**\PostBoostClient\Model\FreeToolGenerateLinkedInHeadlineRequest**](../Model/FreeToolGenerateLinkedInHeadlineRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateLinkedInHeadlineResponse**](../Model/FreeToolGenerateLinkedInHeadlineResponse.md)

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

## `generateSocialPostsFromBlog()`

```php
generateSocialPostsFromBlog($free_tool_generate_social_posts_from_blog_request): \PostBoostClient\Model\FreeToolGenerateSocialPostsFromBlogResponse
```

Turn a blog post (URL or text) into one social post per network with AI (needs a token, spends AI credits)

Turn a blog post (URL or text) into one social post per network with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/blog-to-social-media. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). Each post spends 1 AI credit of the workspace you name (or your active workspace), so a call costs one credit per platform that comes back; results are not cached.

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
$free_tool_generate_social_posts_from_blog_request = {"url":"https://example.com/blog/utm-links","platforms":["x","linkedin"],"tone":"professional","hashtags":"few"}; // \PostBoostClient\Model\FreeToolGenerateSocialPostsFromBlogRequest

try {
    $result = $apiInstance->generateSocialPostsFromBlog($free_tool_generate_social_posts_from_blog_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateSocialPostsFromBlog: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_social_posts_from_blog_request** | [**\PostBoostClient\Model\FreeToolGenerateSocialPostsFromBlogRequest**](../Model/FreeToolGenerateSocialPostsFromBlogRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateSocialPostsFromBlogResponse**](../Model/FreeToolGenerateSocialPostsFromBlogResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateUsernames()`

```php
generateUsernames($free_tool_generate_usernames_request): \PostBoostClient\Model\FreeToolGenerateUsernamesResponse
```

Generate social media usernames

Generate social media usernames. The same logic as the free web tool at https://postboost.co/tools/social-media-username-generator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_generate_usernames_request = {"name":"Maya Green"}; // \PostBoostClient\Model\FreeToolGenerateUsernamesRequest

try {
    $result = $apiInstance->generateUsernames($free_tool_generate_usernames_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateUsernames: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_usernames_request** | [**\PostBoostClient\Model\FreeToolGenerateUsernamesRequest**](../Model/FreeToolGenerateUsernamesRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateUsernamesResponse**](../Model/FreeToolGenerateUsernamesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateYoutubeDescription()`

```php
generateYoutubeDescription($free_tool_generate_youtube_description_request): \PostBoostClient\Model\FreeToolGenerateYoutubeDescriptionResponse
```

Write three YouTube video descriptions with AI (needs a token, spends AI credits)

Write three YouTube video descriptions with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/youtube-description-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

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
$free_tool_generate_youtube_description_request = {"text":"A beginner sourdough bread recipe: feeding the starter, mixing, shaping and baking in a Dutch oven.","keywords":"sourdough bread, beginner","chapters":true,"chapter_lines":["0:00 Intro","1:30 Feeding the starter","4:10 Shaping","9:45 Baking"],"cta":"subscribe"}; // \PostBoostClient\Model\FreeToolGenerateYoutubeDescriptionRequest

try {
    $result = $apiInstance->generateYoutubeDescription($free_tool_generate_youtube_description_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateYoutubeDescription: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_youtube_description_request** | [**\PostBoostClient\Model\FreeToolGenerateYoutubeDescriptionRequest**](../Model/FreeToolGenerateYoutubeDescriptionRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateYoutubeDescriptionResponse**](../Model/FreeToolGenerateYoutubeDescriptionResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `generateYoutubeTitles()`

```php
generateYoutubeTitles($free_tool_generate_youtube_titles_request): \PostBoostClient\Model\FreeToolGenerateYoutubeTitlesResponse
```

Write five YouTube video titles with AI (needs a token, spends AI credits)

Write five YouTube video titles with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/youtube-title-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

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
$free_tool_generate_youtube_titles_request = {"text":"Baking sourdough bread at home for beginners","style":"how-to"}; // \PostBoostClient\Model\FreeToolGenerateYoutubeTitlesRequest

try {
    $result = $apiInstance->generateYoutubeTitles($free_tool_generate_youtube_titles_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->generateYoutubeTitles: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_generate_youtube_titles_request** | [**\PostBoostClient\Model\FreeToolGenerateYoutubeTitlesRequest**](../Model/FreeToolGenerateYoutubeTitlesRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGenerateYoutubeTitlesResponse**](../Model/FreeToolGenerateYoutubeTitlesResponse.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

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

## `getGlossary()`

```php
getGlossary($q, $category): \PostBoostClient\Model\FreeToolGetGlossaryResponse
```

Look up social media terms: plain-language definitions by category, with sources and related terms

Look up social media terms: plain-language definitions by category, with sources and related terms. The same logic as the free web tool at https://postboost.co/tools/social-media-glossary. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$q = 'q_example'; // string
$category = 'category_example'; // string

try {
    $result = $apiInstance->getGlossary($q, $category);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->getGlossary: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **q** | **string**|  | [optional] |
| **category** | **string**|  | [optional] |

### Return type

[**\PostBoostClient\Model\FreeToolGetGlossaryResponse**](../Model/FreeToolGetGlossaryResponse.md)

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

## `getSafeZones()`

```php
getSafeZones($free_tool_get_safe_zones_request): \PostBoostClient\Model\FreeToolGetSafeZonesResponse
```

Get the TikTok, Instagram Reels or YouTube Shorts safe zones for a vertical frame

Get the TikTok, Instagram Reels or YouTube Shorts safe zones for a vertical frame. The same logic as the free web tool at https://postboost.co/tools/safe-zone-checker. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_get_safe_zones_request = {"platform":"tiktok"}; // \PostBoostClient\Model\FreeToolGetSafeZonesRequest

try {
    $result = $apiInstance->getSafeZones($free_tool_get_safe_zones_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->getSafeZones: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_get_safe_zones_request** | [**\PostBoostClient\Model\FreeToolGetSafeZonesRequest**](../Model/FreeToolGetSafeZonesRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolGetSafeZonesResponse**](../Model/FreeToolGetSafeZonesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getVideoSpecs()`

```php
getVideoSpecs($network): \PostBoostClient\Model\FreeToolGetVideoSpecsResponse
```

Get social media video ratios, resolutions, lengths and file size limits per network, with sources

Get social media video ratios, resolutions, lengths and file size limits per network, with sources. The same logic as the free web tool at https://postboost.co/tools/social-media-video-specs. No account needed: call it without a token, or with any API token.

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
    $result = $apiInstance->getVideoSpecs($network);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->getVideoSpecs: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **network** | **string**|  | [optional] |

### Return type

[**\PostBoostClient\Model\FreeToolGetVideoSpecsResponse**](../Model/FreeToolGetVideoSpecsResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAwarenessDays()`

```php
listAwarenessDays($from, $to, $country, $type, $topic): \PostBoostClient\Model\FreeToolListAwarenessDaysResponse
```

List public holidays, awareness days and social media days by date, country, type and topic, with sources

List public holidays, awareness days and social media days by date, country, type and topic, with sources. The same logic as the free web tool at https://postboost.co/tools/social-media-holiday-calendar. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$from = 'from_example'; // string
$to = 'to_example'; // string
$country = 'country_example'; // string
$type = 'type_example'; // string
$topic = 'topic_example'; // string

try {
    $result = $apiInstance->listAwarenessDays($from, $to, $country, $type, $topic);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->listAwarenessDays: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **from** | **string**|  | [optional] |
| **to** | **string**|  | [optional] |
| **country** | **string**|  | [optional] |
| **type** | **string**|  | [optional] |
| **topic** | **string**|  | [optional] |

### Return type

[**\PostBoostClient\Model\FreeToolListAwarenessDaysResponse**](../Model/FreeToolListAwarenessDaysResponse.md)

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

## `pickGiveawayWinners()`

```php
pickGiveawayWinners($free_tool_pick_giveaway_winners_request): \PostBoostClient\Model\FreeToolPickGiveawayWinnersResponse
```

Pick giveaway winners with a draw anyone can verify

Pick giveaway winners with a draw anyone can verify. The same logic as the free web tool at https://postboost.co/tools/giveaway-comment-picker. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_pick_giveaway_winners_request = {"entrants":[{"username":"@Bob","comment":"c"},{"username":"alice","comment":"x"},{"username":"bob","comment":"again"},{"username":"carol"}],"seed":"000102030405060708090a0b0c0d0e0f101112131415161718191a1b1c1d1e1f","winners":2,"alternates":1}; // \PostBoostClient\Model\FreeToolPickGiveawayWinnersRequest

try {
    $result = $apiInstance->pickGiveawayWinners($free_tool_pick_giveaway_winners_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->pickGiveawayWinners: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_pick_giveaway_winners_request** | [**\PostBoostClient\Model\FreeToolPickGiveawayWinnersRequest**](../Model/FreeToolPickGiveawayWinnersRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolPickGiveawayWinnersResponse**](../Model/FreeToolPickGiveawayWinnersResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `pickSocialMediaTool()`

```php
pickSocialMediaTool($free_tool_pick_social_media_tool_request): \PostBoostClient\Model\FreeToolPickSocialMediaToolResponse
```

Match your needs against social media management tools and see what each one misses

Match your needs against social media management tools and see what each one misses. The same logic as the free web tool at https://postboost.co/tools/social-media-tool-picker. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_pick_social_media_tool_request = {"needs":["rest_openapi","mcp","webhooks","free_tier"]}; // \PostBoostClient\Model\FreeToolPickSocialMediaToolRequest

try {
    $result = $apiInstance->pickSocialMediaTool($free_tool_pick_social_media_tool_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->pickSocialMediaTool: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_pick_social_media_tool_request** | [**\PostBoostClient\Model\FreeToolPickSocialMediaToolRequest**](../Model/FreeToolPickSocialMediaToolRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolPickSocialMediaToolResponse**](../Model/FreeToolPickSocialMediaToolResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `planContentCalendar()`

```php
planContentCalendar($free_tool_plan_content_calendar_request): \PostBoostClient\Model\FreeToolPlanContentCalendarResponse
```

Plan a social media content calendar and get it as CSV and ICS

Plan a social media content calendar and get it as CSV and ICS. The same logic as the free web tool at https://postboost.co/tools/social-media-content-calendar-generator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_plan_content_calendar_request = {"start_date":"2026-11-02","weeks":1,"posts_per_week":{"instagram":3,"linkedin":2},"times":{"linkedin":"08:30"},"pillars":["Tips","Product"]}; // \PostBoostClient\Model\FreeToolPlanContentCalendarRequest

try {
    $result = $apiInstance->planContentCalendar($free_tool_plan_content_calendar_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->planContentCalendar: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_plan_content_calendar_request** | [**\PostBoostClient\Model\FreeToolPlanContentCalendarRequest**](../Model/FreeToolPlanContentCalendarRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolPlanContentCalendarResponse**](../Model/FreeToolPlanContentCalendarResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `planPostingFrequency()`

```php
planPostingFrequency($free_tool_plan_posting_frequency_request): \PostBoostClient\Model\FreeToolPlanPostingFrequencyResponse
```

Plan how often to post on each network

Plan how often to post on each network. The same logic as the free web tool at https://postboost.co/tools/posting-frequency-planner. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_plan_posting_frequency_request = {"networks":["instagram","linkedin","tiktok"],"posts_per_week_capacity":12}; // \PostBoostClient\Model\FreeToolPlanPostingFrequencyRequest

try {
    $result = $apiInstance->planPostingFrequency($free_tool_plan_posting_frequency_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->planPostingFrequency: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_plan_posting_frequency_request** | [**\PostBoostClient\Model\FreeToolPlanPostingFrequencyRequest**](../Model/FreeToolPlanPostingFrequencyRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolPlanPostingFrequencyResponse**](../Model/FreeToolPlanPostingFrequencyResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
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

## `scoreSocialAudit()`

```php
scoreSocialAudit($free_tool_score_social_audit_request): \PostBoostClient\Model\FreeToolScoreSocialAuditResponse
```

Score a social media audit checklist and get the top fixes

Score a social media audit checklist and get the top fixes. The same logic as the free web tool at https://postboost.co/tools/social-media-audit-template. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_score_social_audit_request = {"target_posts_per_week":4,"instagram":{"profile":"yes","bio":"yes","link_tracking":"no","frequency":"partly","replies":"yes","native_formats":"yes","pinned":"no","engagement_rate":"partly"},"linkedin":{"profile":"yes","bio":"partly","link_tracking":"no","frequency":"yes","replies":"partly","native_formats":"no","pinned":"yes","engagement_rate":"no"}}; // \PostBoostClient\Model\FreeToolScoreSocialAuditRequest

try {
    $result = $apiInstance->scoreSocialAudit($free_tool_score_social_audit_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->scoreSocialAudit: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_score_social_audit_request** | [**\PostBoostClient\Model\FreeToolScoreSocialAuditRequest**](../Model/FreeToolScoreSocialAuditRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolScoreSocialAuditResponse**](../Model/FreeToolScoreSocialAuditResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `searchEmoji()`

```php
searchEmoji($free_tool_search_emoji_request): \PostBoostClient\Model\FreeToolSearchEmojiResponse
```

Search emoji by name or keyword, to copy and paste into a post

Search emoji by name or keyword, to copy and paste into a post. The same logic as the free web tool at https://postboost.co/tools/social-media-emoji-picker. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_search_emoji_request = {"query":"fire","limit":2}; // \PostBoostClient\Model\FreeToolSearchEmojiRequest

try {
    $result = $apiInstance->searchEmoji($free_tool_search_emoji_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->searchEmoji: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_search_emoji_request** | [**\PostBoostClient\Model\FreeToolSearchEmojiRequest**](../Model/FreeToolSearchEmojiRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolSearchEmojiResponse**](../Model/FreeToolSearchEmojiResponse.md)

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

## `summarizeReport()`

```php
summarizeReport($free_tool_summarize_report_request): \PostBoostClient\Model\FreeToolSummarizeReportResponse
```

Summarize social media post metrics into a report

Summarize social media post metrics into a report. The same logic as the free web tool at https://postboost.co/tools/social-media-report-generator. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_summarize_report_request = {"rows":[{"date":"2026-09-01","network":"linkedin","text":"Launch post: our new planning board","views":2400,"likes":96,"comments":12,"shares":8},{"date":"2026-09-02","network":"instagram","text":"Behind the scenes of the shoot","views":1800,"likes":120,"comments":9,"shares":3},{"date":"2026-09-08","network":"linkedin","text":"Customer story: a bakery's bookings","views":1500,"likes":40,"comments":4,"shares":6}]}; // \PostBoostClient\Model\FreeToolSummarizeReportRequest

try {
    $result = $apiInstance->summarizeReport($free_tool_summarize_report_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->summarizeReport: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_summarize_report_request** | [**\PostBoostClient\Model\FreeToolSummarizeReportRequest**](../Model/FreeToolSummarizeReportRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolSummarizeReportResponse**](../Model/FreeToolSummarizeReportResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `verifyWebhookSignature()`

```php
verifyWebhookSignature($free_tool_verify_webhook_signature_request): \PostBoostClient\Model\FreeToolVerifyWebhookSignatureResponse
```

Verify an HMAC webhook signature

Verify an HMAC webhook signature. The same logic as the free web tool at https://postboost.co/tools/webhook-signature-verifier. No account needed: call it without a token, or with any API token.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new PostBoostClient\Api\FreeToolsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);
$free_tool_verify_webhook_signature_request = {"body":"{\"event\":\"post.published\",\"data\":{\"uuid\":\"0b8f1c2e-6c1d-4f7a-9a51-3d1e2f4a5b6c\"}}","secret":"whsec_test","signature":"a27f6d074108ea6b5df903d3ad4520113a47aa3710cb26c24fab7e36457d915a"}; // \PostBoostClient\Model\FreeToolVerifyWebhookSignatureRequest

try {
    $result = $apiInstance->verifyWebhookSignature($free_tool_verify_webhook_signature_request);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling FreeToolsApi->verifyWebhookSignature: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **free_tool_verify_webhook_signature_request** | [**\PostBoostClient\Model\FreeToolVerifyWebhookSignatureRequest**](../Model/FreeToolVerifyWebhookSignatureRequest.md)|  | |

### Return type

[**\PostBoostClient\Model\FreeToolVerifyWebhookSignatureResponse**](../Model/FreeToolVerifyWebhookSignatureResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
