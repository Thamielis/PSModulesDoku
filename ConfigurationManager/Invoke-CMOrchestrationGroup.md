Invoke-CMOrchestrationGroup
---------------------------




### Synopsis
Start orchestration on an orchestration group.



---


### Description

Use this cmdlet to start orchestration on an orchestration group.



For more information, see Start orchestration (/mem/configmgr/sum/deploy-use/create-orchestration-groups#start-orchestration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMOrchestrationGroup](Get-CMOrchestrationGroup)



* [New-CMOrchestrationGroup](New-CMOrchestrationGroup)



* [Remove-CMOrchestrationGroup](Remove-CMOrchestrationGroup)



* [Set-CMOrchestrationGroup](Set-CMOrchestrationGroup)



* [About orchestration groups in Configuration Manager](About orchestration groups in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Get-CMOrchestrationGroup -Name "IT servers" | Invoke-CMOrchestrationGroup -IgnoreServiceWindow $true
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of orchestration group to start. This value is the MOGID property, which is an integer. For example, `16777217`.






|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Int32]`|true    |named   |False        |MOGId  |



#### **IgnoreServiceWindow**

Set this parameter to `$true` to start the installation immediately and bypass maintenance windows.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**

Specify an object for the orchestration group to start. To get this object, use the Get-CMOrchestrationGroup (Get-CMOrchestrationGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases           |
|-----------------|--------|--------|--------------|------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|OrchestrationGroup|



#### **Name**

Specify the name of the orchestration group to start.






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|true    |named   |False        |OrchestrationGroupName|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Confirm**
-Confirm is an automatic variable that is created when a command has ```[CmdletBinding(SupportsShouldProcess)]```.
-Confirm is used to -Confirm each operation.

If you pass ```-Confirm:$false``` you will not be prompted.


If the command sets a ```[ConfirmImpact("Medium")]``` which is lower than ```$confirmImpactPreference```, you will not be prompted unless -Confirm is passed.

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


### Notes




---


### Syntax
```PowerShell
Invoke-CMOrchestrationGroup [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <Int32> [-IgnoreServiceWindow <Boolean>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMOrchestrationGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-IgnoreServiceWindow <Boolean>] -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMOrchestrationGroup [-DisableWildcardHandling] [-ForceWildcardHandling] [-IgnoreServiceWindow <Boolean>] -Name <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
