Remove-CMCollectionFromDistributionPointGroup
---------------------------------------------




### Synopsis
Removes a collection from distribution point group.



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
#### **CollectionName**








|Type      |Required|Position|PipelineInput|Aliases                                    |
|----------|--------|--------|-------------|-------------------------------------------|
|`[String]`|true    |named   |False        |DeviceCollectionName<br/>UserCollectionName|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointGroupId**








|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |GroupId|



#### **DistributionPointGroupName**








|Type      |Required|Position|PipelineInput|Aliases  |
|----------|--------|--------|-------------|---------|
|`[String]`|true    |named   |False        |GroupName|



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases                            |
|-----------------|--------|--------|--------------|-----------------------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|DeviceCollection<br/>UserCollection|



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
Remove-CMCollectionFromDistributionPointGroup -CollectionName <String> [-DisableWildcardHandling] -DistributionPointGroupId <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromDistributionPointGroup -CollectionName <String> [-DisableWildcardHandling] -DistributionPointGroupName <String> [-Force] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionFromDistributionPointGroup -CollectionName <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```