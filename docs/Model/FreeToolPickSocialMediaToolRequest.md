# # FreeToolPickSocialMediaToolRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**needs** | **string[]** | What you need: team_dashboard (Scheduling dashboard for a team), rest_openapi (REST API with a published OpenAPI spec), sdks (At least one official SDK), mcp (MCP server for AI agents), webhooks (Webhooks), free_tier (Free hosted plan), zapier (Native Zapier app), n8n (Native n8n node), make (Native Make app). Required unless use_case is set. | [optional]
**use_case** | **string** | A shortcut used when needs is left out: team_scheduling (team_dashboard, free_tier), build_app (rest_openapi, sdks, webhooks), ai_agent (mcp, rest_openapi). | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
