# # FreeToolBuildAgentSkillRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**format** | **string** | skill_md (an Agent Skills SKILL.md), agents_md (AGENTS.md) or system_prompt. | [optional] [default to 'skill_md']
**name** | **string** | The skill name, normalised to lowercase letters, digits and hyphens and cut to 64 characters. | [optional] [default to 'postboost-social-media']
**brand** | **string** | The brand the agent works for; omitted when empty. | [optional] [default to '']
**tasks** | **string[]** | What the agent does; the output keeps this enum&#39;s order. | [optional]
**networks** | **string[]** | Networks to add character-limit rules for; none leaves the section out. | [optional]
**autonomy** | **string** | How much the agent may do without asking. | [optional] [default to 'drafts_only']
**daily_cap** | **int** | Posts per day the agent may create; 0 adds no cap line. | [optional] [default to 5]
**brand_voice** | **bool** | Read the workspace brand voice before writing captions. | [optional] [default to true]
**connection** | **string** | connector (the OAuth MCP connector) or api_token (the advanced MCP server with an API key). | [optional] [default to 'connector']
**rules** | **string[]** | Your own do&#39;s and don&#39;ts, one per item. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
