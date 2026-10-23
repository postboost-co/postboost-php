# # FreeToolGenerateBrandVoiceResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**voice** | [**\PostBoostClient\Model\FreeToolGenerateBrandVoiceResponseVoice**](FreeToolGenerateBrandVoiceResponseVoice.md) |  | [optional]
**evidence** | **array<string,string[]>** | Per trait key, up to 2 quotes from your posts that show it; only quotes found in your posts are kept, so a list can be empty. | [optional]
**system_prompt** | **string** | The system prompt PostBoost&#39;s AI uses for this voice; paste it into ChatGPT, Claude or your agent. | [optional]
**markdown** | **string** | The voice as a Markdown guide with its quotes, ending with the system prompt. | [optional]
**credits_spent** | **int** | AI credits this call took from the workspace: 1, or 0 for a cached result. | [optional]
**cached** | **bool** | True when the same request was answered before (free). | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
