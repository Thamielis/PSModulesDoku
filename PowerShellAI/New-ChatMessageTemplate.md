New-ChatMessageTemplate
-----------------------




### Synopsis
Create a new chat message template.



---


### Description


---


### Examples
#### EXAMPLE 1
```PowerShell
New-ChatMessageTemplate -Role 'user' -Content <#string
>
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
|`[Object]`|false   |1       |false        |



#### **Content**

The content of the chat message.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |2       |false        |





---


### Syntax
```PowerShell
New-ChatMessageTemplate [[-Role] <Object>] [[-Content] <Object>] [<CommonParameters>]
```
