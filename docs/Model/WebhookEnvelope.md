# # WebhookEnvelope

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**event** | **string** |  |
**id** | **string** | Delivery ID, one per event. Retries and manual resends repeat it. |
**occurred_at** | **\DateTime** | When the event happened (ISO 8601, UTC). |
**workspace_uuid** | **string** | The workspace the event belongs to (null only on instance-wide system webhooks). Also sent as the &#x60;X-PostBoost-Workspace&#x60; header. |
**data** | **array<string,mixed>** | The post (&#x60;post.*&#x60;, as &#x60;getPost&#x60; returns it, plus &#x60;account&#x60; on per-account events), the account (&#x60;account.*&#x60;) or the reply draft (&#x60;inbox.*&#x60;). |

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
