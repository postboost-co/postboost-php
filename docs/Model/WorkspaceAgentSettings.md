# # WorkspaceAgentSettings

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**horizon_hours** | **int** | Check posts scheduled within this many hours. | [optional] [default to 24]
**check_links** | **bool** | Flag links in captions that answer an HTTP error. | [optional] [default to true]
**banned_phrases** | **string[]** | Phrases to propose removing from captions. | [optional]
**ai_review** | **bool** | Ask AI to review captions (one AI credit per reviewed post). | [optional] [default to false]
**max_ai_reviews_per_run** | **int** |  | [optional] [default to 10]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
