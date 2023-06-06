Get-OpenAIModeration
--------------------




### Synopsis
Checks if prompt contains wording that violates OpenAI moderation rules



---


### Description

Checks prompt text content against latest moderation rules to determine if
any OpenAI moderation rules would be violated.



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-OpenAIModeration -InputText "I want to kill them."
```



---


### Parameters
#### **InputText**

Prompt text to evaluate






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **Raw**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
This function requires the 'OpenAIKey' environment variable to be defined before being invoked
Reference: https://platform.openai.com/docs/guides/moderation/quickstart
Reference: https://platform.openai.com/docs/api-reference/moderations/create



---


### Syntax
```PowerShell
Get-OpenAIModeration [-InputText] <Object> [-Raw] [<CommonParameters>]
```
