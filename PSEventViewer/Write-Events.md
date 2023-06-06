Write-Event
-----------




### Synopsis

Write-Event [[-Computer] <string[]>] [-LogName] <string> [-Source] <string> [[-Category] <int>] [[-EntryType] <EventLogEntryType>] [-ID] <int> [-Message] <string> [[-AdditionalFields] <array>] [<CommonParameters>]




---


### Description


---


### Parameters
#### **AdditionalFields**




|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[array]`|false   |7       |false        |



#### **Category**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|false   |3       |false        |



#### **Computer**




|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[string[]]`|false   |0       |false        |



#### **EntryType**

Valid Values:

* Error
* Warning
* Information
* SuccessAudit
* FailureAudit






|Type                 |Required|Position|PipelineInput|Aliases|
|---------------------|--------|--------|-------------|-------|
|`[EventLogEntryType]`|false   |4       |false        |Level  |



#### **ID**




|Type   |Required|Position|PipelineInput|Aliases|
|-------|--------|--------|-------------|-------|
|`[int]`|true    |5       |false        |EventID|



#### **LogName**




|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[string]`|true    |1       |false        |EventLog|



#### **Message**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |6       |false        |



#### **Source**




|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[string]`|true    |2       |false        |Provider<br/>ProviderName|





---


### Inputs
None




---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Syntax
```PowerShell
syntaxItem
```
```PowerShell
----------
```
```PowerShell
{@{name=Write-Event; CommonParameters=True; parameter=System.Object[]}}
```
