Get-OpenAIModel
---------------




### Synopsis
Get a list of current OpenAI GPT-3 API models



---


### Description

Returns full model properties, or just the names (id values)



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-OpenAIModel
```

#### EXAMPLE 2
```PowerShell
Get-OpenAIModel -Raw
```



---


### Parameters
#### **Name**

The name of the model to return - wildcards are supported






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |1       |false        |



#### **Raw**

Returns the raw JSON response from the API






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
This function requires the 'OpenAIKey' environment variable to be defined before being invoked
Reference: https://platform.openai.com/docs/models/overview
Reference: https://platform.openai.com/docs/api-reference/models



---


### Syntax
```PowerShell
Get-OpenAIModel [[-Name] <Object>] [-Raw] [<CommonParameters>]
```
