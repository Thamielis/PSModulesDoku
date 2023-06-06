Get-OpenAIUsage
---------------




### Synopsis
Get a summary of OpenAI API usage



---


### Description

Returns a summary of OpenAI API usage for your organization. All dates and times are UTC-based, and data may be delayed up to 5 minutes.



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-OpenAIUsage -StartDate '2023-03-01' -EndDate '2023-03-31'
```



---


### Parameters
#### **StartDate**

The Start Date of the usage period to return in YYYY-MM-DD format






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |1       |false        |



#### **EndDate**

The End Date of the usage period to return in YYYY-MM-DD format






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |2       |false        |



#### **OnlyLineItems**




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
Get-OpenAIUsage [[-StartDate] <DateTime>] [[-EndDate] <DateTime>] [-OnlyLineItems] [<CommonParameters>]
```
