# # PreflightResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**valid** | **bool** | True when create-post with the same body would succeed. |
**errors** | **array<string,string[]>** | Validation and network-requirement errors keyed by field, as create-post would report them in a &#x60;422&#x60;. |
**issues** | [**\PostBoostClient\Model\GuardrailError[]**](GuardrailError.md) | Guardrail problems, in the order create-post would report the first of them. |
**publish_at** | **\DateTime** | UTC time the post would publish at; null for a draft. |
**accounts** | [**\PostBoostClient\Model\AccountHealth[]**](AccountHealth.md) |  |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
