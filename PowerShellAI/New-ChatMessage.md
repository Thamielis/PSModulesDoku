New-ChatMessage
---------------




### Synopsis
Create a new chat message.



---


### Description

Create a new chat message and add it to the current chat session.



---


### Examples
#### EXAMPLE 1
```PowerShell
New-ChatMessage -Role 'user' -Content <#string
```



---


### Parameters
#### **Role**

The role of the chat message.
Valid values are 'user', 'system', and 'assistant'.



Valid Values:

* user
* system
* assistant






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **Content**

The content of the chat message.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |2       |false        |





---


### Syntax
```PowerShell
New-ChatMessage [-Role] <Object> [-Content] <Object> [<CommonParameters>]
```
