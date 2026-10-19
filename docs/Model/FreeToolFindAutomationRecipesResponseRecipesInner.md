# # FreeToolFindAutomationRecipesResponseRecipesInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**slug** | **string** | Stable key of the recipe, also its anchor on the page. | [optional]
**title** | **string** | What the recipe does. | [optional]
**trigger** | **string** | What starts it. | [optional]
**goal** | **string** | The result in one or two sentences. | [optional]
**native** | [**\PostBoostClient\Model\FreeToolFindAutomationRecipesResponseRecipesInnerNative**](FreeToolFindAutomationRecipesResponseRecipesInnerNative.md) |  | [optional]
**api_operations** | [**\PostBoostClient\Model\FreeToolFindAutomationRecipesResponseRecipesInnerApiOperationsInner[]**](FreeToolFindAutomationRecipesResponseRecipesInnerApiOperationsInner.md) | The PostBoost API operations the recipe calls. | [optional]
**steps** | [**\PostBoostClient\Model\FreeToolFindAutomationRecipesResponseRecipesInnerSteps**](FreeToolFindAutomationRecipesResponseRecipesInnerSteps.md) |  | [optional]
**n8n_workflow** | **array<string,mixed>** | Importable n8n workflow (core nodes only; add a Header Auth credential named \&quot;PostBoost API token\&quot;) when &#x60;platform&#x60; is &#x60;n8n&#x60;; null otherwise. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
