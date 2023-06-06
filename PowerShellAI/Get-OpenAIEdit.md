Get-OpenAIEdit
--------------




### Synopsis
Given a prompt and an instruction, the model will return an edited version of the prompt



---


### Description

Creates a new edit for the provided input, instruction, and parameters.



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-OpenAIEdit -InputText "What day of the wek is it?" -Instruction "Fix the spelling mistakes"
```



---


### Parameters
#### **InputText**

Prompt text to evaluate






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[Object]`|true    |named   |true (ByValue)|



#### **Instruction**

The instruction that tells the model how to edit the prompt






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |2       |false        |



#### **model**

ID of the model to use. You can use the text-davinci-edit-001 or code-davinci-edit-001 model with this endpoint. Default is code-davinci-edit-001 model



Valid Values:

* text-davinci-edit-001
* code-davinci-edit-001






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |named   |false        |



#### **numberOfEdits**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |named   |false        |



#### **temperature**




|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Decimal]`|false   |named   |false        |



#### **top_p**




|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Decimal]`|false   |named   |false        |



#### **Raw**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Notes
This function requires the 'OpenAIKey' environment variable to be defined before being invoked
Reference: https://platform.openai.com/docs/guides/edits/quickstart
Reference: https://platform.openai.com/docs/api-reference/edits



---


### Syntax
```PowerShell
Get-OpenAIEdit -InputText <Object> [-Instruction] <Object> [-model <Object>] [-numberOfEdits <Object>] [-temperature <Decimal>] [-top_p <Decimal>] [-Raw] [<CommonParameters>]
```
