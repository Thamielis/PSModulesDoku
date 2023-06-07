Set-CMClientSettingSoftwareDeployment
-------------------------------------




### Synopsis
Sets a client setting software deployment.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Schedule**








|Type             |Required|Position|PipelineInput|Aliases           |
|-----------------|--------|--------|-------------|------------------|
|`[IResultObject]`|false   |named   |False        |EvaluationSchedule|



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
Set-CMClientSettingSoftwareDeployment -DefaultSetting [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingSoftwareDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingSoftwareDeployment [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```