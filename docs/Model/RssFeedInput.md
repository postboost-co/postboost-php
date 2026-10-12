# # RssFeedInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | **string** | Public http(s) URL of an RSS 2.0 or Atom feed. |
**name** | **string** |  | [optional]
**account_ids** | **int[]** |  |
**mode** | **string** |  | [optional] [default to 'draft']
**template** | **string** | Post text. Placeholders: &#x60;{title}&#x60;, &#x60;{link}&#x60;, &#x60;{summary}&#x60; (up to 280 characters). Default &#x60;{title}&#x60; + blank line + &#x60;{link}&#x60;. | [optional]
**max_items_per_run** | **int** |  | [optional] [default to 3]
**active** | **bool** |  | [optional] [default to true]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
