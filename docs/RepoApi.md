# Spatio::RepoApi

All URIs are relative to *https://api.spatio.app*

| Method | HTTP request | Description |
| ------ | ------------ | ----------- |
| [**create_repo_branch**](RepoApi.md#create_repo_branch) | **POST** /v1/repos/repositories/{owner}/{repo}/branches | Create a branch (from a base sha). |
| [**create_repo_pull_request**](RepoApi.md#create_repo_pull_request) | **POST** /v1/repos/repositories/{owner}/{repo}/pulls | Open a pull request. |
| [**create_repo_repository**](RepoApi.md#create_repo_repository) | **POST** /v1/repos/repositories | Create a repository. |
| [**get_repo_commit**](RepoApi.md#get_repo_commit) | **GET** /v1/repos/repositories/{owner}/{repo}/commits/{sha} | Fetch a single commit. |
| [**get_repo_repository**](RepoApi.md#get_repo_repository) | **GET** /v1/repos/repositories/{owner}/{repo} | Fetch a single repository. |
| [**link_repo_task**](RepoApi.md#link_repo_task) | **POST** /v1/repos/repositories/{owner}/{repo}/tasks/link | Link an existing Spatio task to this repo, allocating a per-repo number. |
| [**list_repo_branches**](RepoApi.md#list_repo_branches) | **GET** /v1/repos/repositories/{owner}/{repo}/branches | List branches on a repository. |
| [**list_repo_commits**](RepoApi.md#list_repo_commits) | **GET** /v1/repos/repositories/{owner}/{repo}/commits | List commits on a repository. |
| [**list_repo_pull_requests**](RepoApi.md#list_repo_pull_requests) | **GET** /v1/repos/repositories/{owner}/{repo}/pulls | List pull requests on a repository. |
| [**list_repo_repositories**](RepoApi.md#list_repo_repositories) | **GET** /v1/repos/repositories | List the caller&#39;s accessible repositories. |
| [**list_repo_tasks**](RepoApi.md#list_repo_tasks) | **GET** /v1/repos/repositories/{owner}/{repo}/tasks | List tasks linked to this repo (the \&quot;issues\&quot; surface). |
| [**list_repo_workflows**](RepoApi.md#list_repo_workflows) | **GET** /v1/repos/repositories/{owner}/{repo}/workflows | List CI workflows. |
| [**merge_repo_pull_request**](RepoApi.md#merge_repo_pull_request) | **POST** /v1/repos/repositories/{owner}/{repo}/pulls/{number}/merge | Merge a pull request. |
| [**trigger_repo_workflow**](RepoApi.md#trigger_repo_workflow) | **POST** /v1/repos/repositories/{owner}/{repo}/workflows/{id}/trigger | Trigger a workflow_dispatch run. |
| [**workspace_create_repo_branch**](RepoApi.md#workspace_create_repo_branch) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/branches |  |
| [**workspace_create_repo_pull_request**](RepoApi.md#workspace_create_repo_pull_request) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/pulls |  |
| [**workspace_create_repo_repository**](RepoApi.md#workspace_create_repo_repository) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories |  |
| [**workspace_get_repo_commit**](RepoApi.md#workspace_get_repo_commit) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/commits/{sha} |  |
| [**workspace_get_repo_repository**](RepoApi.md#workspace_get_repo_repository) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo} |  |
| [**workspace_link_repo_task**](RepoApi.md#workspace_link_repo_task) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/tasks/link |  |
| [**workspace_list_repo_branches**](RepoApi.md#workspace_list_repo_branches) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/branches |  |
| [**workspace_list_repo_commits**](RepoApi.md#workspace_list_repo_commits) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/commits |  |
| [**workspace_list_repo_pull_requests**](RepoApi.md#workspace_list_repo_pull_requests) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/pulls |  |
| [**workspace_list_repo_repositories**](RepoApi.md#workspace_list_repo_repositories) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories |  |
| [**workspace_list_repo_tasks**](RepoApi.md#workspace_list_repo_tasks) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/tasks |  |
| [**workspace_list_repo_workflows**](RepoApi.md#workspace_list_repo_workflows) | **GET** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/workflows |  |
| [**workspace_merge_repo_pull_request**](RepoApi.md#workspace_merge_repo_pull_request) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/pulls/{number}/merge |  |
| [**workspace_trigger_repo_workflow**](RepoApi.md#workspace_trigger_repo_workflow) | **POST** /v1/organizations/{org}/workspaces/{workspace}/repos/repositories/{owner}/{repo}/workflows/{id}/trigger |  |


## create_repo_branch

> Hash&lt;String, Object&gt; create_repo_branch(owner, repo, request_body)

Create a branch (from a base sha).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Create a branch (from a base sha).
  result = api_instance.create_repo_branch(owner, repo, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->create_repo_branch: #{e}"
end
```

#### Using the create_repo_branch_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_repo_branch_with_http_info(owner, repo, request_body)

```ruby
begin
  # Create a branch (from a base sha).
  data, status_code, headers = api_instance.create_repo_branch_with_http_info(owner, repo, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->create_repo_branch_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_repo_pull_request

> Hash&lt;String, Object&gt; create_repo_pull_request(owner, repo, request_body)

Open a pull request.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Open a pull request.
  result = api_instance.create_repo_pull_request(owner, repo, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->create_repo_pull_request: #{e}"
end
```

#### Using the create_repo_pull_request_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_repo_pull_request_with_http_info(owner, repo, request_body)

```ruby
begin
  # Open a pull request.
  data, status_code, headers = api_instance.create_repo_pull_request_with_http_info(owner, repo, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->create_repo_pull_request_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## create_repo_repository

> Hash&lt;String, Object&gt; create_repo_repository(request_body)

Create a repository.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  # Create a repository.
  result = api_instance.create_repo_repository(request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->create_repo_repository: #{e}"
end
```

#### Using the create_repo_repository_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> create_repo_repository_with_http_info(request_body)

```ruby
begin
  # Create a repository.
  data, status_code, headers = api_instance.create_repo_repository_with_http_info(request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->create_repo_repository_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## get_repo_commit

> Hash&lt;String, Object&gt; get_repo_commit(owner, repo, sha)

Fetch a single commit.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
sha = 'sha_example' # String | 

begin
  # Fetch a single commit.
  result = api_instance.get_repo_commit(owner, repo, sha)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->get_repo_commit: #{e}"
end
```

#### Using the get_repo_commit_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_repo_commit_with_http_info(owner, repo, sha)

```ruby
begin
  # Fetch a single commit.
  data, status_code, headers = api_instance.get_repo_commit_with_http_info(owner, repo, sha)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->get_repo_commit_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **sha** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## get_repo_repository

> Hash&lt;String, Object&gt; get_repo_repository(owner, repo)

Fetch a single repository.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  # Fetch a single repository.
  result = api_instance.get_repo_repository(owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->get_repo_repository: #{e}"
end
```

#### Using the get_repo_repository_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> get_repo_repository_with_http_info(owner, repo)

```ruby
begin
  # Fetch a single repository.
  data, status_code, headers = api_instance.get_repo_repository_with_http_info(owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->get_repo_repository_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## link_repo_task

> Hash&lt;String, Object&gt; link_repo_task(owner, repo, link_repo_task_request)

Link an existing Spatio task to this repo, allocating a per-repo number.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
link_repo_task_request = Spatio::LinkRepoTaskRequest.new({task_id: 'task_id_example'}) # LinkRepoTaskRequest | 

begin
  # Link an existing Spatio task to this repo, allocating a per-repo number.
  result = api_instance.link_repo_task(owner, repo, link_repo_task_request)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->link_repo_task: #{e}"
end
```

#### Using the link_repo_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> link_repo_task_with_http_info(owner, repo, link_repo_task_request)

```ruby
begin
  # Link an existing Spatio task to this repo, allocating a per-repo number.
  data, status_code, headers = api_instance.link_repo_task_with_http_info(owner, repo, link_repo_task_request)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->link_repo_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **link_repo_task_request** | [**LinkRepoTaskRequest**](LinkRepoTaskRequest.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## list_repo_branches

> Hash&lt;String, Object&gt; list_repo_branches(owner, repo)

List branches on a repository.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  # List branches on a repository.
  result = api_instance.list_repo_branches(owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_branches: #{e}"
end
```

#### Using the list_repo_branches_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_repo_branches_with_http_info(owner, repo)

```ruby
begin
  # List branches on a repository.
  data, status_code, headers = api_instance.list_repo_branches_with_http_info(owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_branches_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_repo_commits

> Hash&lt;String, Object&gt; list_repo_commits(owner, repo, opts)

List commits on a repository.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
opts = {
  branch: 'branch_example', # String | 
  limit: 56 # Integer | 
}

begin
  # List commits on a repository.
  result = api_instance.list_repo_commits(owner, repo, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_commits: #{e}"
end
```

#### Using the list_repo_commits_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_repo_commits_with_http_info(owner, repo, opts)

```ruby
begin
  # List commits on a repository.
  data, status_code, headers = api_instance.list_repo_commits_with_http_info(owner, repo, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_commits_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **branch** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_repo_pull_requests

> Hash&lt;String, Object&gt; list_repo_pull_requests(owner, repo)

List pull requests on a repository.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  # List pull requests on a repository.
  result = api_instance.list_repo_pull_requests(owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_pull_requests: #{e}"
end
```

#### Using the list_repo_pull_requests_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_repo_pull_requests_with_http_info(owner, repo)

```ruby
begin
  # List pull requests on a repository.
  data, status_code, headers = api_instance.list_repo_pull_requests_with_http_info(owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_pull_requests_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_repo_repositories

> Hash&lt;String, Object&gt; list_repo_repositories(opts)

List the caller's accessible repositories.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
opts = {
  visibility: 'visibility_example', # String | 
  limit: 56 # Integer | 
}

begin
  # List the caller's accessible repositories.
  result = api_instance.list_repo_repositories(opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_repositories: #{e}"
end
```

#### Using the list_repo_repositories_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_repo_repositories_with_http_info(opts)

```ruby
begin
  # List the caller's accessible repositories.
  data, status_code, headers = api_instance.list_repo_repositories_with_http_info(opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_repositories_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **visibility** | **String** |  | [optional] |
| **limit** | **Integer** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_repo_tasks

> Hash&lt;String, Object&gt; list_repo_tasks(owner, repo, opts)

List tasks linked to this repo (the \"issues\" surface).

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
opts = {
  state: 'open', # String | 
  per_page: 56, # Integer | 
  page: 56 # Integer | 
}

begin
  # List tasks linked to this repo (the \"issues\" surface).
  result = api_instance.list_repo_tasks(owner, repo, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_tasks: #{e}"
end
```

#### Using the list_repo_tasks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_repo_tasks_with_http_info(owner, repo, opts)

```ruby
begin
  # List tasks linked to this repo (the \"issues\" surface).
  data, status_code, headers = api_instance.list_repo_tasks_with_http_info(owner, repo, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_tasks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **state** | **String** |  | [optional] |
| **per_page** | **Integer** |  | [optional] |
| **page** | **Integer** |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## list_repo_workflows

> Hash&lt;String, Object&gt; list_repo_workflows(owner, repo)

List CI workflows.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  # List CI workflows.
  result = api_instance.list_repo_workflows(owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_workflows: #{e}"
end
```

#### Using the list_repo_workflows_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> list_repo_workflows_with_http_info(owner, repo)

```ruby
begin
  # List CI workflows.
  data, status_code, headers = api_instance.list_repo_workflows_with_http_info(owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->list_repo_workflows_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## merge_repo_pull_request

> Hash&lt;String, Object&gt; merge_repo_pull_request(owner, repo, number, opts)

Merge a pull request.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
number = 56 # Integer | 
opts = {
  request_body: { key: 3.56} # Hash<String, Object> | 
}

begin
  # Merge a pull request.
  result = api_instance.merge_repo_pull_request(owner, repo, number, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->merge_repo_pull_request: #{e}"
end
```

#### Using the merge_repo_pull_request_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> merge_repo_pull_request_with_http_info(owner, repo, number, opts)

```ruby
begin
  # Merge a pull request.
  data, status_code, headers = api_instance.merge_repo_pull_request_with_http_info(owner, repo, number, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->merge_repo_pull_request_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **number** | **Integer** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## trigger_repo_workflow

> Hash&lt;String, Object&gt; trigger_repo_workflow(owner, repo, id, opts)

Trigger a workflow_dispatch run.

### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
id = 'id_example' # String | 
opts = {
  request_body: { key: 3.56} # Hash<String, Object> | 
}

begin
  # Trigger a workflow_dispatch run.
  result = api_instance.trigger_repo_workflow(owner, repo, id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->trigger_repo_workflow: #{e}"
end
```

#### Using the trigger_repo_workflow_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> trigger_repo_workflow_with_http_info(owner, repo, id, opts)

```ruby
begin
  # Trigger a workflow_dispatch run.
  data, status_code, headers = api_instance.trigger_repo_workflow_with_http_info(owner, repo, id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->trigger_repo_workflow_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_create_repo_branch

> Hash&lt;String, Object&gt; workspace_create_repo_branch(org, workspace, owner, repo, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_repo_branch(org, workspace, owner, repo, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_create_repo_branch: #{e}"
end
```

#### Using the workspace_create_repo_branch_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_repo_branch_with_http_info(org, workspace, owner, repo, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_repo_branch_with_http_info(org, workspace, owner, repo, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_create_repo_branch_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_create_repo_pull_request

> Hash&lt;String, Object&gt; workspace_create_repo_pull_request(org, workspace, owner, repo, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_repo_pull_request(org, workspace, owner, repo, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_create_repo_pull_request: #{e}"
end
```

#### Using the workspace_create_repo_pull_request_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_repo_pull_request_with_http_info(org, workspace, owner, repo, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_repo_pull_request_with_http_info(org, workspace, owner, repo, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_create_repo_pull_request_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_create_repo_repository

> Hash&lt;String, Object&gt; workspace_create_repo_repository(org, workspace, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_create_repo_repository(org, workspace, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_create_repo_repository: #{e}"
end
```

#### Using the workspace_create_repo_repository_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_create_repo_repository_with_http_info(org, workspace, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_create_repo_repository_with_http_info(org, workspace, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_create_repo_repository_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_get_repo_commit

> Hash&lt;String, Object&gt; workspace_get_repo_commit(org, workspace, owner, repo, sha)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
sha = 'sha_example' # String | 

begin
  
  result = api_instance.workspace_get_repo_commit(org, workspace, owner, repo, sha)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_get_repo_commit: #{e}"
end
```

#### Using the workspace_get_repo_commit_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_repo_commit_with_http_info(org, workspace, owner, repo, sha)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_repo_commit_with_http_info(org, workspace, owner, repo, sha)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_get_repo_commit_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **sha** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_get_repo_repository

> Hash&lt;String, Object&gt; workspace_get_repo_repository(org, workspace, owner, repo)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  
  result = api_instance.workspace_get_repo_repository(org, workspace, owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_get_repo_repository: #{e}"
end
```

#### Using the workspace_get_repo_repository_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_get_repo_repository_with_http_info(org, workspace, owner, repo)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_get_repo_repository_with_http_info(org, workspace, owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_get_repo_repository_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_link_repo_task

> Hash&lt;String, Object&gt; workspace_link_repo_task(org, workspace, owner, repo, request_body)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
request_body = { key: 3.56} # Hash<String, Object> | 

begin
  
  result = api_instance.workspace_link_repo_task(org, workspace, owner, repo, request_body)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_link_repo_task: #{e}"
end
```

#### Using the workspace_link_repo_task_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_link_repo_task_with_http_info(org, workspace, owner, repo, request_body)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_link_repo_task_with_http_info(org, workspace, owner, repo, request_body)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_link_repo_task_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_list_repo_branches

> Hash&lt;String, Object&gt; workspace_list_repo_branches(org, workspace, owner, repo)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  
  result = api_instance.workspace_list_repo_branches(org, workspace, owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_branches: #{e}"
end
```

#### Using the workspace_list_repo_branches_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_repo_branches_with_http_info(org, workspace, owner, repo)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_repo_branches_with_http_info(org, workspace, owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_branches_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_list_repo_commits

> Hash&lt;String, Object&gt; workspace_list_repo_commits(org, workspace, owner, repo)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  
  result = api_instance.workspace_list_repo_commits(org, workspace, owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_commits: #{e}"
end
```

#### Using the workspace_list_repo_commits_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_repo_commits_with_http_info(org, workspace, owner, repo)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_repo_commits_with_http_info(org, workspace, owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_commits_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_list_repo_pull_requests

> Hash&lt;String, Object&gt; workspace_list_repo_pull_requests(org, workspace, owner, repo)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  
  result = api_instance.workspace_list_repo_pull_requests(org, workspace, owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_pull_requests: #{e}"
end
```

#### Using the workspace_list_repo_pull_requests_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_repo_pull_requests_with_http_info(org, workspace, owner, repo)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_repo_pull_requests_with_http_info(org, workspace, owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_pull_requests_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_list_repo_repositories

> Hash&lt;String, Object&gt; workspace_list_repo_repositories(org, workspace)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 

begin
  
  result = api_instance.workspace_list_repo_repositories(org, workspace)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_repositories: #{e}"
end
```

#### Using the workspace_list_repo_repositories_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_repo_repositories_with_http_info(org, workspace)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_repo_repositories_with_http_info(org, workspace)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_repositories_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_list_repo_tasks

> Hash&lt;String, Object&gt; workspace_list_repo_tasks(org, workspace, owner, repo)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  
  result = api_instance.workspace_list_repo_tasks(org, workspace, owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_tasks: #{e}"
end
```

#### Using the workspace_list_repo_tasks_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_repo_tasks_with_http_info(org, workspace, owner, repo)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_repo_tasks_with_http_info(org, workspace, owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_tasks_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_list_repo_workflows

> Hash&lt;String, Object&gt; workspace_list_repo_workflows(org, workspace, owner, repo)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 

begin
  
  result = api_instance.workspace_list_repo_workflows(org, workspace, owner, repo)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_workflows: #{e}"
end
```

#### Using the workspace_list_repo_workflows_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_list_repo_workflows_with_http_info(org, workspace, owner, repo)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_list_repo_workflows_with_http_info(org, workspace, owner, repo)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_list_repo_workflows_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json


## workspace_merge_repo_pull_request

> Hash&lt;String, Object&gt; workspace_merge_repo_pull_request(org, workspace, owner, repo, number, opts)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
number = 56 # Integer | 
opts = {
  request_body: { key: 3.56} # Hash<String, Object> | 
}

begin
  
  result = api_instance.workspace_merge_repo_pull_request(org, workspace, owner, repo, number, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_merge_repo_pull_request: #{e}"
end
```

#### Using the workspace_merge_repo_pull_request_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_merge_repo_pull_request_with_http_info(org, workspace, owner, repo, number, opts)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_merge_repo_pull_request_with_http_info(org, workspace, owner, repo, number, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_merge_repo_pull_request_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **number** | **Integer** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json


## workspace_trigger_repo_workflow

> Hash&lt;String, Object&gt; workspace_trigger_repo_workflow(org, workspace, owner, repo, id, opts)



### Examples

```ruby
require 'time'
require 'spatio-sdk'
# setup authorization
Spatio.configure do |config|
  # Configure Bearer authorization (Personal Access Token (pat_...)): bearerAuth
  config.access_token = 'YOUR_BEARER_TOKEN'
end

api_instance = Spatio::RepoApi.new
org = 'org_example' # String | 
workspace = 'workspace_example' # String | 
owner = 'owner_example' # String | 
repo = 'repo_example' # String | 
id = 'id_example' # String | 
opts = {
  request_body: { key: 3.56} # Hash<String, Object> | 
}

begin
  
  result = api_instance.workspace_trigger_repo_workflow(org, workspace, owner, repo, id, opts)
  p result
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_trigger_repo_workflow: #{e}"
end
```

#### Using the workspace_trigger_repo_workflow_with_http_info variant

This returns an Array which contains the response data, status code and headers.

> <Array(Hash&lt;String, Object&gt;, Integer, Hash)> workspace_trigger_repo_workflow_with_http_info(org, workspace, owner, repo, id, opts)

```ruby
begin
  
  data, status_code, headers = api_instance.workspace_trigger_repo_workflow_with_http_info(org, workspace, owner, repo, id, opts)
  p status_code # => 2xx
  p headers # => { ... }
  p data # => Hash&lt;String, Object&gt;
rescue Spatio::ApiError => e
  puts "Error when calling RepoApi->workspace_trigger_repo_workflow_with_http_info: #{e}"
end
```

### Parameters

| Name | Type | Description | Notes |
| ---- | ---- | ----------- | ----- |
| **org** | **String** |  |  |
| **workspace** | **String** |  |  |
| **owner** | **String** |  |  |
| **repo** | **String** |  |  |
| **id** | **String** |  |  |
| **request_body** | [**Hash&lt;String, Object&gt;**](Object.md) |  | [optional] |

### Return type

**Hash&lt;String, Object&gt;**

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

