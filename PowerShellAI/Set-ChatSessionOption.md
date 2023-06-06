Set-ChatSessionOption
---------------------




### Synopsis
Set a chat session option.



---


### Description


---


### Examples
#### EXAMPLE 1
```PowerShell
Set-ChatSessionOption -model 'gpt-4'
```

#### EXAMPLE 2
```PowerShell
Set-ChatSessionOption -max_tokens 512
```



---


### Parameters
#### **model**

The model to use for the chat session.
Valid values are 'gpt-4' and 'gpt-3.5-turbo'.
Default value is 'gpt-4'.



Valid Values:

* gpt-4
* gpt-3.5-turbo






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |1       |false        |



#### **max_tokens**

The maximum number of tokens to generate.
Default value is 256.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |2       |false        |



#### **temperature**

The temperature of the model.
Default value is 0.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |3       |false        |



#### **top_p**

The top_p of the model.
Default value is 1.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |4       |false        |



#### **frequency_penalty**

The frequency penalty of the model.
Default value is 0.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |5       |false        |



#### **presence_penalty**

The presence penalty of the model.
Default value is 0.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |6       |false        |



#### **stop**

The stop sequence of the model.
Default value is $null.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Object]`|false   |7       |false        |





---


### Syntax
```PowerShell
Set-ChatSessionOption [[-model] <Object>] [[-max_tokens] <Object>] [[-temperature] <Object>] [[-top_p] <Object>] [[-frequency_penalty] <Object>] [[-presence_penalty] <Object>] [[-stop] <Object>] [<CommonParameters>]
```
