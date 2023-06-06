Set-OpenAIKey
-------------




### Synopsis
Set the OpenAI API Key.



---


### Description

Sets the OpenAI API Key using secure string.



---


### Examples
#### EXAMPLE 1
```PowerShell
Set-OpenAIKey -Key (Get-Secret -Name MyOpenAIKey)
```



---


### Parameters
#### **Key**

Specifies OpenAI API Key secure string.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|true    |1       |false        |





---


### Syntax
```PowerShell
Set-OpenAIKey [-Key] <SecureString> [<CommonParameters>]
```
