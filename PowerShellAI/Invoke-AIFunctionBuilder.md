Invoke-AIFunctionBuilder
------------------------




### Synopsis
Create a PowerShell function with the help of ChatGPT



---


### Description

Invoke-AIFunctionBuilder is a function that uses ChatGPT to generate an initial PowerShell function to achieve the goal defined
in the prompt by the user but goes a few steps beyond the typical interaction with an LLM by auto-validating the result
of the AI generated script using parsing techniques that feed common issues back to the model until it resolves them.



---


### Examples
#### EXAMPLE 1
```PowerShell
Invoke-AIFunctionBuilder
# The function builder renders the UI and asks the user to enter a prompt to generate a function
```

#### EXAMPLE 2
```PowerShell
Invoke-AIFunctionBuilder -Prompt "Write a powershell function that will show a date and time in timestamp form" -NonInteractive
function Get-Timestamp {
    return (Get-Date).ToString("yyyy-MM-ddTHH:mm:ss.fffffZ")
}
```

#### EXAMPLE 3
```PowerShell
$function = 'function Write-Hello { Write-Output "hello world" }'
PS>Invoke-AIFunctionBuilder -InitialFunction $function -Prompt "write a powershell function that says hello"
# The function builder renders the UI and validates the function provided meets the goal of the prompt
```



---


### Parameters
#### **Prompt**

A prompt in the format "Write a powershell function that will sing me happy birthday"






|Type      |Required|Position|PipelineInput |
|----------|--------|--------|--------------|
|`[String]`|false   |named   |true (ByValue)|



#### **MaximumReinforcementIterations**

The maximum loop iterations to attempt to generate the function within






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |false        |



#### **NonInteractive**

Return the code result without showing any interactions






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |



#### **Model**

The model to use



Valid Values:

* gpt-3.5-turbo
* gpt-4






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |



#### **InitialFunction**

A seed function to use as the function builder starting point, this can allow you to iterate on an existing idea






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |false        |





---


### Notes
Author: Shaun Lawrie / @shaun_lawrie



---


### Syntax
```PowerShell
Invoke-AIFunctionBuilder [-Prompt <String>] [-MaximumReinforcementIterations <Int32>] [-Model <String>] [-InitialFunction <String>] [<CommonParameters>]
```
```PowerShell
Invoke-AIFunctionBuilder -Prompt <String> [-MaximumReinforcementIterations <Int32>] [-NonInteractive] [-Model <String>] [-InitialFunction <String>] [<CommonParameters>]
```
