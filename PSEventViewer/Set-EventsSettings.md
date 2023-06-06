Set-EventsSettings
------------------




### Synopsis

Set-EventsSettings [-LogName] <string> [[-ComputerName] <string>] [[-MaximumSizeMB] <int>] [[-MaximumSizeInBytes] <int>] [[-EventAction] <string>] [[-Mode] <EventLogMode>] [-WhatIf] [-Confirm] [<CommonParameters>]




---


### Description


---


### Parameters
#### **ComputerName**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |1       |false        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **EventAction**

Valid Values:

* OverwriteEventsAsNeededOldestFirst
* ArchiveTheLogWhenFullDoNotOverwrite
* DoNotOverwriteEventsClearLogManually






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |4       |false        |



#### **LogName**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |0       |false        |



#### **MaximumSizeInBytes**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|false   |3       |false        |



#### **MaximumSizeMB**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|false   |2       |false        |



#### **Mode**

Valid Values:

* Circular
* AutoBackup
* Retain






|Type            |Required|Position|PipelineInput|Aliases|
|----------------|--------|--------|-------------|-------|
|`[EventLogMode]`|false   |5       |false        |LogMode|



#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


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
{@{name=Set-EventsSettings; CommonParameters=True; parameter=System.Object[]}}
```
