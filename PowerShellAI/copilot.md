copilot
-------




### Synopsis
Use GPT to help you remember PowerShell commands and other command line tools



---


### Description

Makes the request to GPT, parses the response and displays it in a box and then prompts the user to run the code or not



---


### Examples
#### EXAMPLE 1
```PowerShell
# via https://twitter.com/ClemMesserli/status/1616312238209376260?s=20&t=KknO2iPk3yrQ7x42ZayS7g
```
copilot "using PowerShell regex, just code. split user from domain of email address with match:  demo.user@google.com"
#### EXAMPLE 2
```PowerShell
copilot 'how to get ImportExcel'
```

#### EXAMPLE 3
```PowerShell
copilot 'processes running with more than 700 handles'
```

#### EXAMPLE 4
```PowerShell
copilot 'processes running with more than 700 handles select first 5, company and name, as json'
```

#### EXAMPLE 5
```PowerShell
copilot 'for each file in the current dir list the name and length'
```

#### EXAMPLE 6
```PowerShell
copilot 'Find all enabled users that have a samaccountname similar to Mazi; List SAMAccountName and DisplayName'
```



---


### Parameters
#### **inputPrompt**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **SystemPrompt**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |2       |false        |



#### **temperature**




|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Decimal]`|false   |3       |false        |



#### **max_tokens**

The maximum number of tokens to generate. default 256






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |4       |false        |



#### **Raw**

Don't show prompt for choice






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Syntax
```PowerShell
copilot [-inputPrompt] <Object> [[-SystemPrompt] <Object>] [[-temperature] <Decimal>] [[-max_tokens] <Object>] [-Raw] [<CommonParameters>]
```
