Invoke-AIExplain
----------------




### Synopsis
Explain the last command or a command by id



---


### Description

Invoke-AIExplain is a function that uses the OpenAI GPT-3 API to provide explain the last command or a command by id.



---


### Examples
#### EXAMPLE 1
```PowerShell
explain
```

#### EXAMPLE 2
```PowerShell
explain 10 # where 10 is the id of the command in the history
```

#### EXAMPLE 3
```PowerShell
explain 10 13 # the start and end id of the commands in the history
```

#### EXAMPLE 4
```PowerShell
explain -Value "Get-Process"
```



---


### Parameters
#### **Id**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |1       |false        |



#### **IdEnd**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |2       |false        |



#### **Value**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |3       |false        |



#### **max_tokens**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |4       |false        |





---


### Syntax
```PowerShell
Invoke-AIExplain [[-Id] <Object>] [[-IdEnd] <Object>] [[-Value] <Object>] [[-max_tokens] <Object>] [<CommonParameters>]
```
