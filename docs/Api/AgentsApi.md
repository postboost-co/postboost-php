# PostBoostClient\AgentsApi

All URIs are relative to https://postboost.co/app/api, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**approveAgentProposal()**](AgentsApi.md#approveAgentProposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/approve | Approve and apply an agent proposal |
| [**createAgent()**](AgentsApi.md#createAgent) | **POST** /{workspaceUuid}/agents | Switch on a background agent |
| [**deleteAgent()**](AgentsApi.md#deleteAgent) | **DELETE** /{workspaceUuid}/agents/{agentUuid} | Delete a background agent |
| [**getAgentRun()**](AgentsApi.md#getAgentRun) | **GET** /{workspaceUuid}/agent-runs/{runUuid} | Get an agent run with its proposals |
| [**listAgentProposals()**](AgentsApi.md#listAgentProposals) | **GET** /{workspaceUuid}/agent-proposals | List agent proposals (approval queue) |
| [**listAgentRuns()**](AgentsApi.md#listAgentRuns) | **GET** /{workspaceUuid}/agents/{agentUuid}/runs | Run history of an agent |
| [**listAgents()**](AgentsApi.md#listAgents) | **GET** /{workspaceUuid}/agents | List background agents |
| [**rejectAgentProposal()**](AgentsApi.md#rejectAgentProposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/reject | Reject an agent proposal |
| [**runAgent()**](AgentsApi.md#runAgent) | **POST** /{workspaceUuid}/agents/{agentUuid}/run | Run a background agent now |
| [**updateAgent()**](AgentsApi.md#updateAgent) | **PUT** /{workspaceUuid}/agents/{agentUuid} | Update a background agent |


## `approveAgentProposal()`

```php
approveAgentProposal($workspace_uuid, $proposal_uuid, $agent_proposal_decision): \PostBoostClient\Model\ApproveAgentProposal200Response
```

Approve and apply an agent proposal

Applies the proposal at once: `hold_post` moves the post back to draft, `edit_caption` replaces the caption. When the post was edited, deleted or left the schedule since the proposal was made, nothing changes and the proposal becomes `stale`. Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$proposal_uuid = 'proposal_uuid_example'; // string
$agent_proposal_decision = new \PostBoostClient\Model\AgentProposalDecision(); // \PostBoostClient\Model\AgentProposalDecision

try {
    $result = $apiInstance->approveAgentProposal($workspace_uuid, $proposal_uuid, $agent_proposal_decision);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->approveAgentProposal: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **proposal_uuid** | **string**|  | |
| **agent_proposal_decision** | [**\PostBoostClient\Model\AgentProposalDecision**](../Model/AgentProposalDecision.md)|  | [optional] |

### Return type

[**\PostBoostClient\Model\ApproveAgentProposal200Response**](../Model/ApproveAgentProposal200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `createAgent()`

```php
createAgent($workspace_uuid, $workspace_agent_input): \PostBoostClient\Model\CreateAgent201Response
```

Switch on a background agent

Creates an agent (one per type per workspace). It first runs within five minutes, then on its `schedule`. **Pre-publish checker** looks at posts scheduled in the next `horizon_hours` and proposes holding (back to draft) posts that would fail: disconnected accounts, network requirements, daily caps, the X allowance and links that answer an error. It proposes caption edits that drop `banned_phrases`. With `ai_review: true` it also asks AI to review up to `max_ai_reviews_per_run` posts per run (one AI credit each). Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$workspace_agent_input = {"type":"pre_publish_checker","schedule":"hourly","settings":{"horizon_hours":24,"banned_phrases":["guaranteed"]}}; // \PostBoostClient\Model\WorkspaceAgentInput

try {
    $result = $apiInstance->createAgent($workspace_uuid, $workspace_agent_input);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->createAgent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **workspace_agent_input** | [**\PostBoostClient\Model\WorkspaceAgentInput**](../Model/WorkspaceAgentInput.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateAgent201Response**](../Model/CreateAgent201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `deleteAgent()`

```php
deleteAgent($workspace_uuid, $agent_uuid): \PostBoostClient\Model\DeleteAgent200Response
```

Delete a background agent

Removes the agent. Its run history and proposals stay. Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$agent_uuid = 'agent_uuid_example'; // string

try {
    $result = $apiInstance->deleteAgent($workspace_uuid, $agent_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->deleteAgent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **agent_uuid** | **string**|  | |

### Return type

[**\PostBoostClient\Model\DeleteAgent200Response**](../Model/DeleteAgent200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `getAgentRun()`

```php
getAgentRun($workspace_uuid, $run_uuid): \PostBoostClient\Model\RunAgent202Response
```

Get an agent run with its proposals

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$run_uuid = 'run_uuid_example'; // string

try {
    $result = $apiInstance->getAgentRun($workspace_uuid, $run_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->getAgentRun: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **run_uuid** | **string**|  | |

### Return type

[**\PostBoostClient\Model\RunAgent202Response**](../Model/RunAgent202Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAgentProposals()`

```php
listAgentProposals($workspace_uuid, $status, $per_page, $page): \PostBoostClient\Model\ListAgentProposals200Response
```

List agent proposals (approval queue)

Proposals of all agents in the workspace, newest first. Defaults to `pending`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$status = 'pending'; // string
$per_page = 20; // int
$page = 56; // int

try {
    $result = $apiInstance->listAgentProposals($workspace_uuid, $status, $per_page, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->listAgentProposals: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **status** | **string**|  | [optional] [default to &#39;pending&#39;] |
| **per_page** | **int**|  | [optional] [default to 20] |
| **page** | **int**|  | [optional] |

### Return type

[**\PostBoostClient\Model\ListAgentProposals200Response**](../Model/ListAgentProposals200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAgentRuns()`

```php
listAgentRuns($workspace_uuid, $agent_uuid, $per_page, $page): \PostBoostClient\Model\ListAgentRuns200Response
```

Run history of an agent

Runs of the agent, newest first, with what each checked and proposed and the AI credits it used.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$agent_uuid = 'agent_uuid_example'; // string
$per_page = 20; // int
$page = 56; // int

try {
    $result = $apiInstance->listAgentRuns($workspace_uuid, $agent_uuid, $per_page, $page);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->listAgentRuns: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **agent_uuid** | **string**|  | |
| **per_page** | **int**|  | [optional] [default to 20] |
| **page** | **int**|  | [optional] |

### Return type

[**\PostBoostClient\Model\ListAgentRuns200Response**](../Model/ListAgentRuns200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `listAgents()`

```php
listAgents($workspace_uuid): \PostBoostClient\Model\ListAgents200Response
```

List background agents

Background agents switched on for the workspace. Agents run on a schedule, record every run and never change a post themselves: each change is a proposal that a workspace admin or member approves. Available type: `pre_publish_checker`.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.

try {
    $result = $apiInstance->listAgents($workspace_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->listAgents: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |

### Return type

[**\PostBoostClient\Model\ListAgents200Response**](../Model/ListAgents200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `rejectAgentProposal()`

```php
rejectAgentProposal($workspace_uuid, $proposal_uuid, $agent_proposal_decision): \PostBoostClient\Model\ApproveAgentProposal200Response
```

Reject an agent proposal

Records the rejection (and optional note); nothing changes on the post. Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$proposal_uuid = 'proposal_uuid_example'; // string
$agent_proposal_decision = new \PostBoostClient\Model\AgentProposalDecision(); // \PostBoostClient\Model\AgentProposalDecision

try {
    $result = $apiInstance->rejectAgentProposal($workspace_uuid, $proposal_uuid, $agent_proposal_decision);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->rejectAgentProposal: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **proposal_uuid** | **string**|  | |
| **agent_proposal_decision** | [**\PostBoostClient\Model\AgentProposalDecision**](../Model/AgentProposalDecision.md)|  | [optional] |

### Return type

[**\PostBoostClient\Model\ApproveAgentProposal200Response**](../Model/ApproveAgentProposal200Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `runAgent()`

```php
runAgent($workspace_uuid, $agent_uuid): \PostBoostClient\Model\RunAgent202Response
```

Run a background agent now

Queues a run outside the schedule (`trigger: manual`). Six per hour. Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$agent_uuid = 'agent_uuid_example'; // string

try {
    $result = $apiInstance->runAgent($workspace_uuid, $agent_uuid);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->runAgent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **agent_uuid** | **string**|  | |

### Return type

[**\PostBoostClient\Model\RunAgent202Response**](../Model/RunAgent202Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `updateAgent()`

```php
updateAgent($workspace_uuid, $agent_uuid, $workspace_agent_update): \PostBoostClient\Model\CreateAgent201Response
```

Update a background agent

Changes the name, schedule, settings or `enabled`. Settings you leave out keep their value. Admins and members only.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure Bearer authorization: bearerAuth
$config = PostBoostClient\Configuration::getDefaultConfiguration()->setAccessToken('YOUR_ACCESS_TOKEN');


$apiInstance = new PostBoostClient\Api\AgentsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$workspace_uuid = 'workspace_uuid_example'; // string | UUID of the workspace.
$agent_uuid = 'agent_uuid_example'; // string
$workspace_agent_update = new \PostBoostClient\Model\WorkspaceAgentUpdate(); // \PostBoostClient\Model\WorkspaceAgentUpdate

try {
    $result = $apiInstance->updateAgent($workspace_uuid, $agent_uuid, $workspace_agent_update);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AgentsApi->updateAgent: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **workspace_uuid** | **string**| UUID of the workspace. | |
| **agent_uuid** | **string**|  | |
| **workspace_agent_update** | [**\PostBoostClient\Model\WorkspaceAgentUpdate**](../Model/WorkspaceAgentUpdate.md)|  | |

### Return type

[**\PostBoostClient\Model\CreateAgent201Response**](../Model/CreateAgent201Response.md)

### Authorization

[bearerAuth](../../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)
