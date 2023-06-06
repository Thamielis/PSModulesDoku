Get-OpenAIEmbeddings
--------------------




### Synopsis
Get OpenAI Embeddings



---


### Description

Get OpenAI Embeddings



---


### Related Links
* [https://platform.openai.com/docs/api-reference/embeddings](https://platform.openai.com/docs/api-reference/embeddings)





---


### Examples
#### EXAMPLE 1
```PowerShell
Get-OpenAIEmbeddings -Content "Hello world"
```



---


### Parameters
#### **Content**

The text to embed






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |false        |



#### **Raw**

Return the raw response






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Syntax
```PowerShell
Get-OpenAIEmbeddings [-Content] <String> [-Raw] [<CommonParameters>]
```
