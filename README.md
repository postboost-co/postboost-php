# PostBoost PHP SDK

Official PHP client for the [PostBoost API](https://postboost.co/docs/api).

## Install

```bash
composer require postboost/php-sdk
```

| | |
|---|---|
| **Packagist** | [packagist.org/packages/postboost/php-sdk](https://packagist.org/packages/postboost/php-sdk) |
| **GitHub** | [postboost-co/postboost-php](https://github.com/postboost-co/postboost-php) |
| **Docs** | [postboost.co/docs/api](https://postboost.co/docs/api) |
| **Version** | v1.27.0 |

## Quick start

```php
use PostBoost\Client\Api\PostsApi;
use PostBoost\Client\Configuration;

$config = Configuration::getDefaultConfiguration()
    ->setAccessToken('YOUR_API_TOKEN');

$api = new PostsApi(new \GuzzleHttp\Client(), $config);
$posts = $api->listPosts('YOUR_WORKSPACE_UUID');
foreach ($posts as $post) {
    echo $post->getUuid() . PHP_EOL;
}
```

---

## API Endpoints

All URIs are relative to *https://postboost.co/app/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AIApi* | [**blogToSocial**](docs/Api/AIApi.md#blogtosocial) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post
*AIApi* | [**deleteBrandVoice**](docs/Api/AIApi.md#deletebrandvoice) | **DELETE** /{workspaceUuid}/brand-voice | Delete the brand voice
*AIApi* | [**getAIUsage**](docs/Api/AIApi.md#getaiusage) | **GET** /{workspaceUuid}/usage/ai | AI credit usage
*AIApi* | [**getBrandVoice**](docs/Api/AIApi.md#getbrandvoice) | **GET** /{workspaceUuid}/brand-voice | Get the brand voice
*AIApi* | [**getRepurposeRun**](docs/Api/AIApi.md#getrepurposerun) | **GET** /{workspaceUuid}/ai/repurpose/runs/{runId} | Get a repurpose run
*AIApi* | [**imageAltText**](docs/Api/AIApi.md#imagealttext) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI
*AIApi* | [**imageEdit**](docs/Api/AIApi.md#imageedit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI
*AIApi* | [**imageGenerate**](docs/Api/AIApi.md#imagegenerate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption
*AIApi* | [**imagePrompt**](docs/Api/AIApi.md#imageprompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption
*AIApi* | [**imageVariations**](docs/Api/AIApi.md#imagevariations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image
*AIApi* | [**learnBrandVoice**](docs/Api/AIApi.md#learnbrandvoice) | **POST** /{workspaceUuid}/brand-voice/learn | Learn a brand voice from past posts
*AIApi* | [**repurposeContent**](docs/Api/AIApi.md#repurposecontent) | **POST** /{workspaceUuid}/ai/repurpose | Repurpose long-form content into a draft post set with a carousel
*AIApi* | [**updateBrandVoice**](docs/Api/AIApi.md#updatebrandvoice) | **PUT** /{workspaceUuid}/brand-voice | Create or update the brand voice
*AccountGroupsApi* | [**createAccountGroup**](docs/Api/AccountGroupsApi.md#createaccountgroup) | **POST** /{workspaceUuid}/account-groups | Create an account group
*AccountGroupsApi* | [**deleteAccountGroup**](docs/Api/AccountGroupsApi.md#deleteaccountgroup) | **DELETE** /{workspaceUuid}/account-groups/{accountGroupUuid} | Delete an account group
*AccountGroupsApi* | [**getAccountGroup**](docs/Api/AccountGroupsApi.md#getaccountgroup) | **GET** /{workspaceUuid}/account-groups/{accountGroupUuid} | Get an account group
*AccountGroupsApi* | [**listAccountGroups**](docs/Api/AccountGroupsApi.md#listaccountgroups) | **GET** /{workspaceUuid}/account-groups | List account groups
*AccountGroupsApi* | [**updateAccountGroup**](docs/Api/AccountGroupsApi.md#updateaccountgroup) | **PUT** /{workspaceUuid}/account-groups/{accountGroupUuid} | Update an account group
*AccountsApi* | [**connectChannel**](docs/Api/AccountsApi.md#connectchannel) | **POST** /{workspaceUuid}/accounts/connect/{provider} | Connect a Telegram, Discord or Slack channel
*AccountsApi* | [**createConnectLink**](docs/Api/AccountsApi.md#createconnectlink) | **POST** /{workspaceUuid}/accounts/connect-links | Create a connect link
*AccountsApi* | [**createReconnectLink**](docs/Api/AccountsApi.md#createreconnectlink) | **POST** /{workspaceUuid}/accounts/{accountUuid}/reconnect-links | Create a reconnect link
*AccountsApi* | [**getAccount**](docs/Api/AccountsApi.md#getaccount) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
*AccountsApi* | [**getAccountHealth**](docs/Api/AccountsApi.md#getaccounthealth) | **GET** /{workspaceUuid}/account-health | Account health
*AccountsApi* | [**listAccounts**](docs/Api/AccountsApi.md#listaccounts) | **GET** /{workspaceUuid}/accounts | List accounts
*ActivityApi* | [**listApiActivity**](docs/Api/ActivityApi.md#listapiactivity) | **GET** /{workspaceUuid}/activity | List API activity
*AgentsApi* | [**approveAgentProposal**](docs/Api/AgentsApi.md#approveagentproposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/approve | Approve and apply an agent proposal
*AgentsApi* | [**createAgent**](docs/Api/AgentsApi.md#createagent) | **POST** /{workspaceUuid}/agents | Switch on a background agent
*AgentsApi* | [**deleteAgent**](docs/Api/AgentsApi.md#deleteagent) | **DELETE** /{workspaceUuid}/agents/{agentUuid} | Delete a background agent
*AgentsApi* | [**getAgentRun**](docs/Api/AgentsApi.md#getagentrun) | **GET** /{workspaceUuid}/agent-runs/{runUuid} | Get an agent run with its proposals
*AgentsApi* | [**listAgentProposals**](docs/Api/AgentsApi.md#listagentproposals) | **GET** /{workspaceUuid}/agent-proposals | List agent proposals (approval queue)
*AgentsApi* | [**listAgentRuns**](docs/Api/AgentsApi.md#listagentruns) | **GET** /{workspaceUuid}/agents/{agentUuid}/runs | Run history of an agent
*AgentsApi* | [**listAgents**](docs/Api/AgentsApi.md#listagents) | **GET** /{workspaceUuid}/agents | List background agents
*AgentsApi* | [**rejectAgentProposal**](docs/Api/AgentsApi.md#rejectagentproposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/reject | Reject an agent proposal
*AgentsApi* | [**runAgent**](docs/Api/AgentsApi.md#runagent) | **POST** /{workspaceUuid}/agents/{agentUuid}/run | Run a background agent now
*AgentsApi* | [**updateAgent**](docs/Api/AgentsApi.md#updateagent) | **PUT** /{workspaceUuid}/agents/{agentUuid} | Update a background agent
*AnalyticsApi* | [**createReportExport**](docs/Api/AnalyticsApi.md#createreportexport) | **POST** /{workspaceUuid}/reports/exports | Create a report export
*AnalyticsApi* | [**downloadReportExport**](docs/Api/AnalyticsApi.md#downloadreportexport) | **GET** /{workspaceUuid}/reports/exports/{exportUuid}/download | Download a report file
*AnalyticsApi* | [**getAccountAnalytics**](docs/Api/AnalyticsApi.md#getaccountanalytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics
*AnalyticsApi* | [**getAnalyticsSummary**](docs/Api/AnalyticsApi.md#getanalyticssummary) | **GET** /{workspaceUuid}/analytics | Get analytics summary
*AnalyticsApi* | [**getBestPostingTimes**](docs/Api/AnalyticsApi.md#getbestpostingtimes) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times
*AnalyticsApi* | [**getPostAnalytics_0**](docs/Api/AnalyticsApi.md#getpostanalytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
*AnalyticsApi* | [**getPostingTimes**](docs/Api/AnalyticsApi.md#getpostingtimes) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap
*AnalyticsApi* | [**getReportBranding**](docs/Api/AnalyticsApi.md#getreportbranding) | **GET** /{workspaceUuid}/report-branding | Get the report branding
*AnalyticsApi* | [**getReportExport**](docs/Api/AnalyticsApi.md#getreportexport) | **GET** /{workspaceUuid}/reports/exports/{exportUuid} | Get a report export
*AnalyticsApi* | [**listReportExports**](docs/Api/AnalyticsApi.md#listreportexports) | **GET** /{workspaceUuid}/reports/exports | List report exports
*AnalyticsApi* | [**updateReportBranding**](docs/Api/AnalyticsApi.md#updatereportbranding) | **PUT** /{workspaceUuid}/report-branding | Update the report branding
*AnalyticsApi* | [**uploadReportBrandingLogo**](docs/Api/AnalyticsApi.md#uploadreportbrandinglogo) | **POST** /{workspaceUuid}/report-branding/logo | Upload the report logo
*CompetitorsApi* | [**addCompetitor**](docs/Api/CompetitorsApi.md#addcompetitor) | **POST** /{workspaceUuid}/competitors | Track a competitor
*CompetitorsApi* | [**deleteCompetitor**](docs/Api/CompetitorsApi.md#deletecompetitor) | **DELETE** /{workspaceUuid}/competitors/{competitorId} | Stop tracking a competitor
*CompetitorsApi* | [**getCompetitor**](docs/Api/CompetitorsApi.md#getcompetitor) | **GET** /{workspaceUuid}/competitors/{competitorId} | Get a competitor
*CompetitorsApi* | [**listCompetitors**](docs/Api/CompetitorsApi.md#listcompetitors) | **GET** /{workspaceUuid}/competitors | List competitors
*FreeToolsApi* | [**buildUtmUrl**](docs/Api/FreeToolsApi.md#buildutmurl) | **POST** /tools/utm-builder | Build a UTM-tagged campaign URL
*FreeToolsApi* | [**calculateEngagementRate**](docs/Api/FreeToolsApi.md#calculateengagementrate) | **POST** /tools/engagement-rate-calculator | Calculate an engagement rate
*FreeToolsApi* | [**checkPost**](docs/Api/FreeToolsApi.md#checkpost) | **POST** /tools/social-media-post-checker | Check a post against each network&#39;s publishing rules
*FreeToolsApi* | [**cleanText**](docs/Api/FreeToolsApi.md#cleantext) | **POST** /tools/ai-text-cleaner | Clean AI-written text: dashes, quotes, invisible characters, markdown
*FreeToolsApi* | [**countCharacters**](docs/Api/FreeToolsApi.md#countcharacters) | **POST** /tools/social-media-character-counter | Count characters as each network counts them
*FreeToolsApi* | [**formatLinkedInPost**](docs/Api/FreeToolsApi.md#formatlinkedinpost) | **POST** /tools/linkedin-post-formatter | Format a LinkedIn post with bold, italic and lists
*FreeToolsApi* | [**generateFancyText**](docs/Api/FreeToolsApi.md#generatefancytext) | **POST** /tools/fancy-text-generator | Convert text to fancy Unicode styles
*FreeToolsApi* | [**listFreeTools**](docs/Api/FreeToolsApi.md#listfreetools) | **GET** /tools | List the free tools
*FreeToolsApi* | [**splitThread**](docs/Api/FreeToolsApi.md#splitthread) | **POST** /tools/x-thread-maker | Split long text into a thread
*HashtagGroupsApi* | [**createHashtagGroup**](docs/Api/HashtagGroupsApi.md#createhashtaggroup) | **POST** /{workspaceUuid}/hashtag-groups | Create a hashtag group
*HashtagGroupsApi* | [**deleteHashtagGroup**](docs/Api/HashtagGroupsApi.md#deletehashtaggroup) | **DELETE** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Delete a hashtag group
*HashtagGroupsApi* | [**getHashtagGroup**](docs/Api/HashtagGroupsApi.md#gethashtaggroup) | **GET** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Get a hashtag group
*HashtagGroupsApi* | [**listHashtagGroups**](docs/Api/HashtagGroupsApi.md#listhashtaggroups) | **GET** /{workspaceUuid}/hashtag-groups | List hashtag groups
*HashtagGroupsApi* | [**updateHashtagGroup**](docs/Api/HashtagGroupsApi.md#updatehashtaggroup) | **PUT** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Update a hashtag group
*InboxApi* | [**approveInboxReplyDraft**](docs/Api/InboxApi.md#approveinboxreplydraft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/approve | Approve and send a reply draft
*InboxApi* | [**createInboxReplyDraft**](docs/Api/InboxApi.md#createinboxreplydraft) | **POST** /{workspaceUuid}/inbox/conversations/{conversationId}/drafts | Draft a reply
*InboxApi* | [**deleteInboxReplyDraft**](docs/Api/InboxApi.md#deleteinboxreplydraft) | **DELETE** /{workspaceUuid}/inbox/drafts/{draftId} | Withdraw a reply draft
*InboxApi* | [**getInboxConversation**](docs/Api/InboxApi.md#getinboxconversation) | **GET** /{workspaceUuid}/inbox/conversations/{conversationId} | Get an inbox conversation
*InboxApi* | [**getInboxReplyDraft**](docs/Api/InboxApi.md#getinboxreplydraft) | **GET** /{workspaceUuid}/inbox/drafts/{draftId} | Get a reply draft
*InboxApi* | [**listInboxConversations**](docs/Api/InboxApi.md#listinboxconversations) | **GET** /{workspaceUuid}/inbox/conversations | List inbox conversations
*InboxApi* | [**listInboxReplyDrafts**](docs/Api/InboxApi.md#listinboxreplydrafts) | **GET** /{workspaceUuid}/inbox/drafts | List reply drafts
*InboxApi* | [**rejectInboxReplyDraft**](docs/Api/InboxApi.md#rejectinboxreplydraft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/reject | Reject a reply draft
*InboxApi* | [**updateInboxConversation**](docs/Api/InboxApi.md#updateinboxconversation) | **PATCH** /{workspaceUuid}/inbox/conversations/{conversationId} | Update an inbox conversation
*InboxApi* | [**updateInboxReplyDraft**](docs/Api/InboxApi.md#updateinboxreplydraft) | **PUT** /{workspaceUuid}/inbox/drafts/{draftId} | Edit a reply draft
*MediaApi* | [**abortChunkedUpload**](docs/Api/MediaApi.md#abortchunkedupload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload
*MediaApi* | [**completeChunkedUpload**](docs/Api/MediaApi.md#completechunkedupload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload
*MediaApi* | [**createMediaFolder**](docs/Api/MediaApi.md#createmediafolder) | **POST** /{workspaceUuid}/media/folders | Create media folder
*MediaApi* | [**deleteMediaBulk**](docs/Api/MediaApi.md#deletemediabulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk)
*MediaApi* | [**deleteMediaFolder**](docs/Api/MediaApi.md#deletemediafolder) | **DELETE** /{workspaceUuid}/media/folders/{folderUuid} | Delete media folder
*MediaApi* | [**getMedia**](docs/Api/MediaApi.md#getmedia) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media
*MediaApi* | [**getRemoteUploadStatus**](docs/Api/MediaApi.md#getremoteuploadstatus) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status
*MediaApi* | [**initiateChunkedUpload**](docs/Api/MediaApi.md#initiatechunkedupload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload
*MediaApi* | [**initiateRemoteUpload**](docs/Api/MediaApi.md#initiateremoteupload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload
*MediaApi* | [**listMedia**](docs/Api/MediaApi.md#listmedia) | **GET** /{workspaceUuid}/media | List media
*MediaApi* | [**listMediaFolders**](docs/Api/MediaApi.md#listmediafolders) | **GET** /{workspaceUuid}/media/folders | List media folders
*MediaApi* | [**updateMedia**](docs/Api/MediaApi.md#updatemedia) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media
*MediaApi* | [**updateMediaFolder**](docs/Api/MediaApi.md#updatemediafolder) | **PUT** /{workspaceUuid}/media/folders/{folderUuid} | Update media folder
*MediaApi* | [**uploadChunk**](docs/Api/MediaApi.md#uploadchunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk
*MediaApi* | [**uploadMedia**](docs/Api/MediaApi.md#uploadmedia) | **POST** /{workspaceUuid}/media | Upload media (binary)
*MediaApi* | [**uploadMediaBase64**](docs/Api/MediaApi.md#uploadmediabase64) | **POST** /{workspaceUuid}/media/base64 | Upload media (base64 JSON)
*MentionsApi* | [**createMention**](docs/Api/MentionsApi.md#createmention) | **POST** /{workspaceUuid}/mentions | Create mention
*MentionsApi* | [**deleteMention**](docs/Api/MentionsApi.md#deletemention) | **DELETE** /{workspaceUuid}/mentions/{mentionId} | Delete mention
*MentionsApi* | [**getMention**](docs/Api/MentionsApi.md#getmention) | **GET** /{workspaceUuid}/mentions/{mentionId} | Get mention
*MentionsApi* | [**listMentions**](docs/Api/MentionsApi.md#listmentions) | **GET** /{workspaceUuid}/mentions | List mentions
*MentionsApi* | [**updateMention**](docs/Api/MentionsApi.md#updatemention) | **PUT** /{workspaceUuid}/mentions/{mentionId} | Update mention
*PostingScheduleApi* | [**getPostingSchedule**](docs/Api/PostingScheduleApi.md#getpostingschedule) | **GET** /{workspaceUuid}/posting-schedule | Get the posting schedule
*PostingScheduleApi* | [**getRecommendedPostingTimes**](docs/Api/PostingScheduleApi.md#getrecommendedpostingtimes) | **GET** /{workspaceUuid}/posting-schedule/recommended | Get recommended posting times
*PostingScheduleApi* | [**listQueueSlots**](docs/Api/PostingScheduleApi.md#listqueueslots) | **GET** /{workspaceUuid}/queue/slots | List upcoming queue slots
*PostingScheduleApi* | [**resetAccountPostingSchedule**](docs/Api/PostingScheduleApi.md#resetaccountpostingschedule) | **DELETE** /{workspaceUuid}/posting-schedule/{accountId} | Reset an account schedule
*PostingScheduleApi* | [**updatePostingSchedule**](docs/Api/PostingScheduleApi.md#updatepostingschedule) | **PUT** /{workspaceUuid}/posting-schedule | Set the posting schedule
*PostsApi* | [**addPostToQueue**](docs/Api/PostsApi.md#addposttoqueue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
*PostsApi* | [**approvePost**](docs/Api/PostsApi.md#approvepost) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
*PostsApi* | [**createPost**](docs/Api/PostsApi.md#createpost) | **POST** /{workspaceUuid}/posts | Create post
*PostsApi* | [**createRecyclingRule**](docs/Api/PostsApi.md#createrecyclingrule) | **POST** /{workspaceUuid}/recycling-rules | Create a recycling rule
*PostsApi* | [**createRssFeed**](docs/Api/PostsApi.md#createrssfeed) | **POST** /{workspaceUuid}/rss-feeds | Add an RSS feed
*PostsApi* | [**deletePost**](docs/Api/PostsApi.md#deletepost) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
*PostsApi* | [**deletePostsBulk**](docs/Api/PostsApi.md#deletepostsbulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
*PostsApi* | [**deleteRecyclingRule**](docs/Api/PostsApi.md#deleterecyclingrule) | **DELETE** /{workspaceUuid}/recycling-rules/{ruleUuid} | Delete a recycling rule
*PostsApi* | [**deleteRssFeed**](docs/Api/PostsApi.md#deleterssfeed) | **DELETE** /{workspaceUuid}/rss-feeds/{feedUuid} | Delete an RSS feed
*PostsApi* | [**getPost**](docs/Api/PostsApi.md#getpost) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
*PostsApi* | [**getPostAnalytics**](docs/Api/PostsApi.md#getpostanalytics) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
*PostsApi* | [**getRecyclingRule**](docs/Api/PostsApi.md#getrecyclingrule) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid} | Get a recycling rule
*PostsApi* | [**getRssFeed**](docs/Api/PostsApi.md#getrssfeed) | **GET** /{workspaceUuid}/rss-feeds/{feedUuid} | Get an RSS feed
*PostsApi* | [**listPosts**](docs/Api/PostsApi.md#listposts) | **GET** /{workspaceUuid}/posts | List posts
*PostsApi* | [**listRecyclingRules**](docs/Api/PostsApi.md#listrecyclingrules) | **GET** /{workspaceUuid}/recycling-rules | List recycling rules
*PostsApi* | [**listRecyclingRuns**](docs/Api/PostsApi.md#listrecyclingruns) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid}/runs | List a recycling rule&#39;s runs
*PostsApi* | [**listRssFeeds**](docs/Api/PostsApi.md#listrssfeeds) | **GET** /{workspaceUuid}/rss-feeds | List RSS feeds
*PostsApi* | [**pollRssFeed**](docs/Api/PostsApi.md#pollrssfeed) | **POST** /{workspaceUuid}/rss-feeds/{feedUuid}/poll | Check an RSS feed now
*PostsApi* | [**recyclePost**](docs/Api/PostsApi.md#recyclepost) | **POST** /{workspaceUuid}/posts/{postUuid}/recycle | Recycle a post on an interval
*PostsApi* | [**retryPostAccount**](docs/Api/PostsApi.md#retrypostaccount) | **POST** /{workspaceUuid}/posts/retry/{postUuid}/{accountUuid} | Retry publishing to one account
*PostsApi* | [**schedulePost**](docs/Api/PostsApi.md#schedulepost) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
*PostsApi* | [**updatePost**](docs/Api/PostsApi.md#updatepost) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post
*PostsApi* | [**updateRecyclingRule**](docs/Api/PostsApi.md#updaterecyclingrule) | **PUT** /{workspaceUuid}/recycling-rules/{ruleUuid} | Update, pause or resume a recycling rule
*PostsApi* | [**updateRssFeed**](docs/Api/PostsApi.md#updaterssfeed) | **PUT** /{workspaceUuid}/rss-feeds/{feedUuid} | Update, pause or resume an RSS feed
*PostsApi* | [**validatePost**](docs/Api/PostsApi.md#validatepost) | **POST** /{workspaceUuid}/posts/validate | Validate post (dry run)
*ReceiptsApi* | [**createReceipt**](docs/Api/ReceiptsApi.md#createreceipt) | **POST** /panel/receipts | Create receipt
*ReceiptsApi* | [**deleteReceipt**](docs/Api/ReceiptsApi.md#deletereceipt) | **DELETE** /panel/receipts/{receiptUuid} | Delete receipt
*ReceiptsApi* | [**deleteReceiptsBulk**](docs/Api/ReceiptsApi.md#deletereceiptsbulk) | **DELETE** /panel/receipts | Delete receipts (bulk)
*ReceiptsApi* | [**getReceipt**](docs/Api/ReceiptsApi.md#getreceipt) | **GET** /panel/receipts/{receiptUuid} | Get receipt
*ReceiptsApi* | [**listReceipts**](docs/Api/ReceiptsApi.md#listreceipts) | **GET** /panel/receipts | List receipts
*ReceiptsApi* | [**updateReceipt**](docs/Api/ReceiptsApi.md#updatereceipt) | **PUT** /panel/receipts/{receiptUuid} | Update receipt
*SubscriptionsApi* | [**addGenericSubscription**](docs/Api/SubscriptionsApi.md#addgenericsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/generic | Add generic subscription
*SubscriptionsApi* | [**cancelSubscription**](docs/Api/SubscriptionsApi.md#cancelsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/cancel | Cancel subscription
*SubscriptionsApi* | [**changeSubscriptionPlan**](docs/Api/SubscriptionsApi.md#changesubscriptionplan) | **PUT** /panel/workspaces/{workspaceUuid}/subscription/change-plan | Change subscription plan
*SubscriptionsApi* | [**checkoutSubscription**](docs/Api/SubscriptionsApi.md#checkoutsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/new | New subscription checkout
*SubscriptionsApi* | [**createSubscription**](docs/Api/SubscriptionsApi.md#createsubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription | Create subscription
*SubscriptionsApi* | [**deleteSubscription**](docs/Api/SubscriptionsApi.md#deletesubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription | Delete subscription
*SubscriptionsApi* | [**getSubscription**](docs/Api/SubscriptionsApi.md#getsubscription) | **GET** /panel/workspaces/{workspaceUuid}/subscription | Get subscription
*SubscriptionsApi* | [**removeGenericSubscription**](docs/Api/SubscriptionsApi.md#removegenericsubscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription/generic | Remove generic subscription
*SubscriptionsApi* | [**resumeSubscription**](docs/Api/SubscriptionsApi.md#resumesubscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/resume | Resume subscription
*SubscriptionsApi* | [**updateSubscription**](docs/Api/SubscriptionsApi.md#updatesubscription) | **PUT** /panel/workspaces/{workspaceUuid}/subscription | Update subscription
*TagsApi* | [**createTag**](docs/Api/TagsApi.md#createtag) | **POST** /{workspaceUuid}/tags | Create tag
*TagsApi* | [**deleteTag**](docs/Api/TagsApi.md#deletetag) | **DELETE** /{workspaceUuid}/tags/{tagUuid} | Delete tag
*TagsApi* | [**getTag**](docs/Api/TagsApi.md#gettag) | **GET** /{workspaceUuid}/tags/{tagUuid} | Get tag
*TagsApi* | [**listTags**](docs/Api/TagsApi.md#listtags) | **GET** /{workspaceUuid}/tags | List tags
*TagsApi* | [**updateTag**](docs/Api/TagsApi.md#updatetag) | **PUT** /{workspaceUuid}/tags/{tagUuid} | Update tag
*TemplatesApi* | [**createTemplate**](docs/Api/TemplatesApi.md#createtemplate) | **POST** /{workspaceUuid}/templates | Create a template
*TemplatesApi* | [**deleteTemplate**](docs/Api/TemplatesApi.md#deletetemplate) | **DELETE** /{workspaceUuid}/templates/{templateId} | Delete a template
*TemplatesApi* | [**getTemplate**](docs/Api/TemplatesApi.md#gettemplate) | **GET** /{workspaceUuid}/templates/{templateId} | Get a template
*TemplatesApi* | [**listTemplates**](docs/Api/TemplatesApi.md#listtemplates) | **GET** /{workspaceUuid}/templates | List templates
*TemplatesApi* | [**updateTemplate**](docs/Api/TemplatesApi.md#updatetemplate) | **PUT** /{workspaceUuid}/templates/{templateId} | Update a template
*UsersApi* | [**createUser**](docs/Api/UsersApi.md#createuser) | **POST** /panel/users | Create user
*UsersApi* | [**deleteUser**](docs/Api/UsersApi.md#deleteuser) | **DELETE** /panel/users/{userId} | Delete user
*UsersApi* | [**deleteUsersBulk**](docs/Api/UsersApi.md#deleteusersbulk) | **DELETE** /panel/users | Delete users (bulk)
*UsersApi* | [**getUser**](docs/Api/UsersApi.md#getuser) | **GET** /panel/users/{userId} | Get user
*UsersApi* | [**listUsers**](docs/Api/UsersApi.md#listusers) | **GET** /panel/users | List users
*UsersApi* | [**updateUser**](docs/Api/UsersApi.md#updateuser) | **PUT** /panel/users/{userId} | Update user
*WebhooksApi* | [**createWebhookSubscription**](docs/Api/WebhooksApi.md#createwebhooksubscription) | **POST** /{workspaceUuid}/webhooks/subscriptions | Subscribe a webhook
*WebhooksApi* | [**deleteWebhookSubscription**](docs/Api/WebhooksApi.md#deletewebhooksubscription) | **DELETE** /{workspaceUuid}/webhooks/subscriptions/{subscriptionUuid} | Unsubscribe a webhook
*WebhooksApi* | [**listWebhookSubscriptions**](docs/Api/WebhooksApi.md#listwebhooksubscriptions) | **GET** /{workspaceUuid}/webhooks/subscriptions | List webhook subscriptions
*WorkspacesApi* | [**addUserToWorkspace**](docs/Api/WorkspacesApi.md#addusertoworkspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
*WorkspacesApi* | [**createApiKey**](docs/Api/WorkspacesApi.md#createapikey) | **POST** /{workspaceUuid}/api-keys | Create a scoped API key
*WorkspacesApi* | [**createResellerClient**](docs/Api/WorkspacesApi.md#createresellerclient) | **POST** /{workspaceUuid}/clients | Create a client workspace
*WorkspacesApi* | [**createWorkspace**](docs/Api/WorkspacesApi.md#createworkspace) | **POST** /panel/workspaces | Create workspace
*WorkspacesApi* | [**deleteApiKey**](docs/Api/WorkspacesApi.md#deleteapikey) | **DELETE** /{workspaceUuid}/api-keys/{apiKeyId} | Revoke a scoped API key
*WorkspacesApi* | [**deleteWorkspace**](docs/Api/WorkspacesApi.md#deleteworkspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
*WorkspacesApi* | [**deleteWorkspacesBulk**](docs/Api/WorkspacesApi.md#deleteworkspacesbulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
*WorkspacesApi* | [**getWorkspace**](docs/Api/WorkspacesApi.md#getworkspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
*WorkspacesApi* | [**getWorkspaceAICredits**](docs/Api/WorkspacesApi.md#getworkspaceaicredits) | **GET** /panel/workspaces/{workspaceUuid}/ai-credits | Get workspace AI credits
*WorkspacesApi* | [**getXUsage**](docs/Api/WorkspacesApi.md#getxusage) | **GET** /{workspaceUuid}/usage/x | X (Twitter) usage
*WorkspacesApi* | [**listApiKeys**](docs/Api/WorkspacesApi.md#listapikeys) | **GET** /{workspaceUuid}/api-keys | List scoped API keys
*WorkspacesApi* | [**listMyWorkspaces**](docs/Api/WorkspacesApi.md#listmyworkspaces) | **GET** /workspaces | List my workspaces
*WorkspacesApi* | [**listResellerClients**](docs/Api/WorkspacesApi.md#listresellerclients) | **GET** /{workspaceUuid}/clients | List client workspaces
*WorkspacesApi* | [**listWorkspaces**](docs/Api/WorkspacesApi.md#listworkspaces) | **GET** /panel/workspaces | List workspaces
*WorkspacesApi* | [**removeUserFromWorkspace**](docs/Api/WorkspacesApi.md#removeuserfromworkspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
*WorkspacesApi* | [**updateWorkspace**](docs/Api/WorkspacesApi.md#updateworkspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
*WorkspacesApi* | [**updateWorkspaceUser**](docs/Api/WorkspacesApi.md#updateworkspaceuser) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace

---

## Links

- Docs and quick start: https://postboost.co/docs/quickstart
- API reference: https://postboost.co/docs/api
- MCP server for AI agents: https://postboost.co/docs/mcp
- All PostBoost open-source projects: https://github.com/postboost-co
- Awesome PostBoost: https://github.com/postboost-co/awesome-postboost

## Authentication

Create an API token in PostBoost under **Settings → Access Tokens** and pass it as a Bearer token. Never commit tokens; read them from an environment variable such as `POSTBOOST_API_TOKEN`.

## Contributing

This PHP SDK is generated from the [PostBoost OpenAPI spec](https://postboost.co/docs/api). Bugs and feature requests: open an issue in [postboost-php](https://github.com/postboost-co/postboost-php/issues). Generated code is overwritten on every release, so fixes usually land in the spec or the generator templates; see [CONTRIBUTING.md](CONTRIBUTING.md).

Security issues: see [SECURITY.md](SECURITY.md). Questions: hi@postboost.co.

## License

MIT, see [LICENSE](LICENSE).

---

## Links

- Docs and quick start: https://postboost.co/docs/quickstart
- API reference: https://postboost.co/docs/api
- MCP server for AI agents: https://postboost.co/docs/mcp
- All PostBoost open-source projects: https://github.com/postboost-co
- Awesome PostBoost: https://github.com/postboost-co/awesome-postboost

## Authentication

Create an API token in PostBoost under **Settings → Access Tokens** and pass it as a Bearer token. Never commit tokens; read them from an environment variable such as `POSTBOOST_API_TOKEN`.

## Contributing

This PHP SDK is generated from the [PostBoost OpenAPI spec](https://postboost.co/docs/api). Bugs and feature requests: open an issue in [postboost-php](https://github.com/postboost-co/postboost-php/issues). Generated code is overwritten on every release, so fixes usually land in the spec or the generator templates; see [CONTRIBUTING.md](CONTRIBUTING.md).

Security issues: see [SECURITY.md](SECURITY.md). Questions: hi@postboost.co.

## License

MIT, see [LICENSE](LICENSE).
