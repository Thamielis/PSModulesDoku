NBCopilot
---------




### Synopsis
Interactes with GPT and sends the result to a Polyglot Interactive Notebook cell



---


### Description


---


### Examples
#### EXAMPLE 1
```PowerShell
NBCopilot 'Write a PowerShell core function, just code, no explanation, do not show how to use it, that will: show a date and time in timestamp form'
```

#### EXAMPLE 2
```PowerShell
NBCopilot 'add comment based help to your code'
```

#### EXAMPLE 3
```PowerShell
$prompt = 'Write c#, just the function, no explanation, do not show how to use it, that will: show a date and time in a regular timestamp form'
```
NBCopilot $prompt -cellType csharp


---


### Parameters
#### **prompt**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |1       |false        |



#### **cellType**

Valid Values:

* pwsh
* csharp
* fsharp
* html
* markdown
* javascript
* sql
* mermaid
* kql






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |2       |false        |





---


### Syntax
```PowerShell
NBCopilot [[-prompt] <Object>] [[-cellType] <Object>] [<CommonParameters>]
```
