Get-CMOrchestrationGroupScript
------------------------------




### Synopsis

Get-CMOrchestrationGroupScript [-InputObject] <IResultObject#SMS_MachineOrchestrationGroup> -ScriptType <OrchestrationScriptTypes> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]

Get-CMOrchestrationGroupScript -ScriptGuid <string> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]

Get-CMOrchestrationGroupScript -MOGID <int> -ScriptType <OrchestrationScriptTypes> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]

Get-CMOrchestrationGroupScript -MOGName <string> -ScriptType <OrchestrationScriptTypes> [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]




---


### Description


---


### Parameters
#### **DisableWildcardHandling**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **ForceWildcardHandling**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[switch]`|false   |Named   |false        |



#### **InputObject**




|Type                                           |Required|Position|PipelineInput |Aliases           |
|-----------------------------------------------|--------|--------|--------------|------------------|
|`[IResultObject#SMS_MachineOrchestrationGroup]`|true    |0       |true (ByValue)|OrchestrationGroup|



#### **MOGID**




|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[int]`|true    |Named   |false        |



#### **MOGName**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |Named   |false        |



#### **ScriptGuid**




|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[string]`|true    |Named   |false        |



#### **ScriptType**

Valid Values:

* Pre
* Post






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[OrchestrationScriptTypes]`|true    |Named   |false        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject




---


### Outputs
* IResultObject#SMS_MachineOrchestrationGroupScript







---


### Syntax
```PowerShell
syntaxItem
```
```PowerShell
----------
```
```PowerShell
{@{name=Get-CMOrchestrationGroupScript; CommonParameters=True; parameter=System.Object[]}, @{name=Get-CMOrchestrationGroupScript; CommonParameters=True; parameter=System.Object[]}, @{name=Get-CMOrchest…
```
