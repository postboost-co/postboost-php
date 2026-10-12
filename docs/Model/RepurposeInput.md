# # RepurposeInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source_type** | **string** |  |
**url** | **string** | Article URL (&#x60;url&#x60;) or YouTube video URL (&#x60;youtube&#x60;). For &#x60;text&#x60;, an optional link to mention. | [optional]
**pdf_url** | **string** | Public URL of a PDF (&#x60;pdf&#x60;), at most 20 MB. | [optional]
**title** | **string** | Required for &#x60;text&#x60;. For &#x60;youtube&#x60;, overrides the video title. | [optional]
**text** | **string** | Required for &#x60;text&#x60;. Long sources are cut to about 12,000 characters. | [optional]
**transcript** | **string** | Video transcript for &#x60;youtube&#x60;. | [optional]
**platforms** | **string[]** | Limit to connected accounts of these networks. Ignored when &#x60;account_ids&#x60; is set. | [optional]
**account_ids** | **int[]** | Target accounts. Default is every connected account. | [optional]
**tone** | **string** |  | [optional] [default to 'engaging']
**content_length** | **string** |  | [optional] [default to 'medium']
**hashtags** | **string** |  | [optional] [default to 'few']
**cta** | **string** |  | [optional] [default to 'none']
**language** | **string** |  | [optional] [default to 'auto']
**custom_instructions** | **string** |  | [optional]
**carousel** | **bool** | Render carousel slides (one extra AI credit for the outline). | [optional] [default to true]
**slide_count** | **int** | Total slides including the hook and call-to-action slides. | [optional] [default to 7]
**theme** | [**\PostBoostClient\Model\RepurposeInputTheme**](RepurposeInputTheme.md) |  | [optional]
**create_post** | **bool** | Create the draft post. &#x60;false&#x60; returns captions and slides only. | [optional] [default to true]
**use_brand_voice** | **bool** |  | [optional] [default to true]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
