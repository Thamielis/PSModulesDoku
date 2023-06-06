Get-GPT3Completion
------------------




### Synopsis
Get a completion from the OpenAI GPT-3 API



---


### Description

Given a prompt, the model will return one or more predicted completions, and can also return the probabilities of alternative tokens at each position



---


### Examples
#### EXAMPLE 1
```PowerShell
Get-GPT3Completion -prompt "What is 2%2? - please explain"
```



---


### Parameters
#### **prompt**

The prompt to generate completions for






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|true    |1       |false        |



#### **model**

ID of the model to use. Defaults to 'text-davinci-003'






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |2       |false        |



#### **temperature**

The temperature used to control the model's likelihood to take risky actions. Higher values means the model will take more risks. Try 0.9 for more creative applications, and 0 (argmax sampling) for ones with a well-defined answer. Defaults to 0






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Decimal]`|false   |3       |false        |



#### **max_tokens**

The maximum number of tokens to generate. By default, this will be 64 if the prompt is not provided, and 1 if a prompt is provided. The maximum is 2048






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |4       |false        |



#### **top_p**

An alternative to sampling with temperature, called nucleus sampling, where the model considers the results of the tokens with top_p probability mass. So 0.1 means only the tokens comprising the top 10% probability mass are considered. Defaults to 1






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Decimal]`|false   |5       |false        |



#### **frequency_penalty**

A value between 0 and 1 that penalizes new tokens based on whether they appear in the text so far. Defaults to 0






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Decimal]`|false   |6       |false        |



#### **presence_penalty**

A value between 0 and 1 that penalizes new tokens based on whether they appear in the text so far. Defaults to 0






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Decimal]`|false   |7       |false        |



#### **stop**

A list of tokens that will cause the API to stop generating further tokens. By default, the API will stop generating when it hits one of the following tokens: ., !, or ?.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |8       |false        |



#### **Raw**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |false        |





---


### Syntax
```PowerShell
Get-GPT3Completion [-prompt] <Object> [[-model] <Object>] [[-temperature] <Decimal>] [[-max_tokens] <Int32>] [[-top_p] <Decimal>] [[-frequency_penalty] <Decimal>] [[-presence_penalty] <Decimal>] [[-stop] <Object>] [-Raw] [<CommonParameters>]
```
