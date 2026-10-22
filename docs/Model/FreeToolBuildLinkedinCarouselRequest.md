# # FreeToolBuildLinkedinCarouselRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **string** | The post or outline. Blank lines separate slides; a first line starting with # (or a short first line without closing punctuation that is not a list item) is the slide heading; - * • lines become bullets. |
**max_slides** | **int** | Most slides to return, 3 to 20. The cover and the CTA slide are always kept. | [optional] [default to 10]
**size** | **string** | Slide shape: &#x60;4:5&#x60; (1080 × 1350) or &#x60;1:1&#x60; (1080 × 1080). Every page of a LinkedIn document has the same size. | [optional] [default to '4:5']
**cover** | **bool** | Start with a cover slide: the first heading, or the first line of the text. | [optional] [default to true]
**cta** | **string** | Text of a closing call-to-action slide. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
