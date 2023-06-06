Get-OpenAIUser
--------------




### Synopsis
Get OpenAI User Information



---


### Description

Returns an overview of the user's OpenAI organization information



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-OpenAIUser -OrganizationId 'org-IkLeiQaK1fZi6271T9u18jO5'
```



---


### Parameters
#### **OrganizationId**

The Identifier for this organization sometimes used in API requests






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |





---


### Notes
This function requires the 'OpenAIKey' environment variable to be defined before being invoked
Reference: https://platform.openai.com/docs/models/overview
Reference: https://platform.openai.com/docs/api-reference/models



---


### Syntax
```PowerShell
Get-OpenAIUser [-OrganizationId] <String> [<CommonParameters>]
```
