Invoke-OpenAIAPI
----------------




### Synopsis
Invoke the OpenAI API



---


### Description

Invoke the OpenAI API



---


### Examples
#### EXAMPLE 1
```PowerShell
Invoke-OpenAIAPI -Uri "https://api.openai.com/v1/images/generations" -Method Post -Body $body
```



---


### Parameters
#### **Uri**

The URI to invoke






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **Method**

The HTTP method to use. Defaults to 'Get'



Valid Values:

* Default
* Delete
* Get
* Head
* Merge
* Options
* Patch
* Post
* Put
* Trace






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |2       |false        |



#### **Body**

The body to send with the request






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |3       |false        |



#### **NoProgress**

The option to hide write-progress if you want, you could also set $ProgressPreference to SilentlyContinue






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Syntax
```PowerShell
Invoke-OpenAIAPI [-Uri] <Object> [[-Method] <Object>] [[-Body] <Object>] [-NoProgress] [<CommonParameters>]
```
