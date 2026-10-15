# # FreeToolCleanTextRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **string** |  |
**dashes** | **string** | What replaces an em or en dash between words: \&quot;, \&quot; (comma), \&quot;-\&quot; (hyphen), \&quot; - \&quot; (spaced) or nothing (keep). Number ranges like 2020–2024 always get a hyphen. | [optional] [default to 'comma']
**quotes** | **bool** | Curly quotes and apostrophes to straight ones. | [optional] [default to true]
**invisible** | **bool** | Remove zero-width characters and soft hyphens; turn non-breaking and thin spaces into normal spaces. | [optional] [default to true]
**spaces** | **bool** | Collapse double spaces between words and remove spaces at line ends. | [optional] [default to true]
**ellipsis** | **bool** | The ellipsis character to three dots. | [optional] [default to true]
**markdown** | **bool** | Strip **bold**, __bold__, *italic* and _italic_ markers, keeping the words. | [optional] [default to true]
**flag_phrases** | **bool** | List common AI phrases (e.g. \&quot;delve\&quot;) with their offsets. They are never changed. | [optional] [default to true]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
