# # FreeToolCheckReadabilityResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**supported** | **bool** | False for a language other than English: no scores, hints or suggestions. | [optional]
**note** | **string** | Why the text was not scored, or null. | [optional]
**flesch_reading_ease** | **float** | Flesch reading ease, one decimal: higher is easier, 60-70 is plain English. Null when not scored. | [optional]
**flesch_kincaid_grade** | **float** | Flesch-Kincaid grade level, one decimal: the US school grade that can read the text. Null when not scored. | [optional]
**sentences** | **int** | Sentences with at least one word. | [optional]
**words** | **int** | Words, not counting hashtags, @mentions, links and emoji. | [optional]
**syllables** | **int** | Syllables, by the heuristic described in the docs. | [optional]
**avg_words_per_sentence** | **float** | Words per sentence, one decimal. | [optional]
**long_sentences** | [**\PostBoostClient\Model\FreeToolCheckReadabilityResponseLongSentencesInner[]**](FreeToolCheckReadabilityResponseLongSentencesInner.md) | Sentences of more than 25 words. | [optional]
**passive_hints** | **int** | Possible passive phrases (\&quot;was written\&quot;, \&quot;is being reviewed\&quot;). A hint, not a grammar check. | [optional]
**emoji_count** | **int** | Emoji (Extended_Pictographic characters). | [optional]
**hashtag_count** | **int** | Hashtags. | [optional]
**suggestions** | **string[]** | Plain fixes, e.g. which sentence to split. Empty when the text reads easily. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
