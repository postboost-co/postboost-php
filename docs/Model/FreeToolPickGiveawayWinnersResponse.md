# # FreeToolPickGiveawayWinnersResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**winners** | **string[]** | Entrant keys in the drawn order. | [optional]
**alternates** | **string[]** | Entrant keys drawn after the winners, in order. | [optional]
**entrants_before** | **int** | Comments received. | [optional]
**entrants_after** | **int** | Entries left after the filters: the length of entrant_list. | [optional]
**entrant_list** | **string[]** | The canonical entrant list to publish: keys sorted by UTF-8 bytes. Joined with \&quot;\\n\&quot; it is what entrants_hash hashes. | [optional]
**entrants_hash** | **string** | SHA-256 (hex) of the canonical entrant list. | [optional]
**fingerprint** | **string** | SHA-256 (hex) of the seed bytes: what to publish before the entries close. | [optional]
**seed** | **string** | The seed used, lowercase hex. Publish it after the draw. | [optional]
**pre_committed** | **bool** | False when the seed was generated for this draw, so no fingerprint could be published before it. | [optional]
**algorithm** | **string** |  | [optional]
**warnings** | [**\PostBoostClient\Model\FreeToolCheckPostResponseNetworksInnerErrorsInner[]**](FreeToolCheckPostResponseNetworksInnerErrorsInner.md) | Codes: not_enough_entrants, not_pre_committed. | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)
