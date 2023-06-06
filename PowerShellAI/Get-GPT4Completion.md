Get-GPT4Completion
------------------




### Synopsis
Get a GPT-4 completion.



---


### Description

Get a GPT-4 completion from the OpenAI API.



---


### Examples
#### EXAMPLE 1
```PowerShell
chat "use powershell: what is my IP address?"
```

#### EXAMPLE 2
```PowerShell
Get-GPT4Completion -Prompt <#string
>
```



---


### Parameters
#### **Content**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **temperature**




|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Decimal]`|false   |2       |false        |





---


### Syntax
```PowerShell
Get-GPT4Completion [-Content] <Object> [[-temperature] <Decimal>] [<CommonParameters>]
```
