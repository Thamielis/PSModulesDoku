Set-AzureOpenAI
---------------




### Synopsis
Sets the Azure OpenAI API endpoint, deployment name, API version, and API key.



---


### Description

Sets up Azure OpenAI as the chat API provider. Use `Set-ChatAPIProvider -Provider OpenAI` to point to the public OpenAI



---


### Examples
#### EXAMPLE 1
```PowerShell
Set-AzureOpenAI `
    -Endpoint https://anEndpoint.openai.azure.com/ `
    -DeploymentName aName `
    -ApiVersion 2023-03-15-preview `
    -ApiKey aKey
```



---


### Parameters
#### **Endpoint**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **DeploymentName**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |2       |false        |



#### **ApiVersion**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |3       |false        |



#### **ApiKey**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |4       |false        |





---


### Syntax
```PowerShell
Set-AzureOpenAI [-Endpoint] <Object> [-DeploymentName] <Object> [-ApiVersion] <Object> [-ApiKey] <Object> [<CommonParameters>]
```
