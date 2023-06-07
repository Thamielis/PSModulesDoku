Deny-CMOrchestrationGroupScript
-------------------------------




### Synopsis

Deny-CMOrchestrationGroupScript -InputObject <IResultObject#SMS_MachineOrchestrationGroupScript> [-Comment <string>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]

Deny-CMOrchestrationGroupScript -ScriptGuid <string> [-Comment <string>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-WhatIf] [-Confirm] [<CommonParameters>]




---


### Description


---


### Parameters
#### **Comment**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|false   |Named   |false        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

#### **DisableWildcardHandling**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **ForceWildcardHandling**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **InputObject**




|Type                                                 |Required|Position|PipelineInput |
|-----------------------------------------------------|--------|--------|--------------|
|`[IResultObject#SMS_MachineOrchestrationGroupScript]`|true    |Named   |true (ByValue)|



#### **ScriptGuid**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |Named   |false        |



#### **WhatIf**
-WhatIf is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-WhatIf is used to see what would happen, or return operations without executing them


---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject




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
{@{name=Deny-CMOrchestrationGroupScript; CommonParameters=True; parameter=System.Object[]}, @{name=Deny-CMOrchestrationGroupScript; CommonParameters=True; parameter=System.Object[]}}
```
