Remove-CMMaintenanceWindow
--------------------------




### Synopsis
Remove a maintenance window.



---


### Description

Use this cmdlet to remove a maintenance window from a collection.



For more information on maintenance windows, see How to use maintenance windows in Configuration Manager (/mem/configmgr/core/clients/manage/collections/use-maintenance-windows).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMMaintenanceWindow](Get-CMMaintenanceWindow)



* [New-CMMaintenanceWindow](New-CMMaintenanceWindow)



* [Set-CMMaintenanceWindow](Set-CMMaintenanceWindow)



* [How to use maintenance windows in Configuration Manager](How to use maintenance windows in Configuration Manager)





---


### Examples
#### Example 1: Remove a maintenance window by name from a collection by ID
```PowerShell
Remove-CMMaintenanceWindow -Name "Distribution Point Maintenance" -CollectionId "XYZ0004D"
```

#### Example 2: Remove all maintenance windows on a collection
```PowerShell
$coll = Get-CMCollection -CollectionId "XYZ0003f"
Remove-CMMaintenanceWindow -InputObject $coll -MaintenanceWindowName "*" -Force
```



---


### Parameters
#### **CollectionId**

Specify the ID of a collection from which to remove the maintenance window. This ID is a standard collection ID, for example `XYZ0003F`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **CollectionName**

Specify the name of a collection from which to remove the maintenance window.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Force**

Add this parameter to force the command to run without asking for user confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an object for a collection from which to remove the maintenance window. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|Collection<br/>Site|



#### **MaintenanceWindowName**

Specify the name of a maintenance window to remove from the targeted collection.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



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
Remove-CMMaintenanceWindow [-CollectionId] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -MaintenanceWindowName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMMaintenanceWindow [-CollectionName] <String> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -MaintenanceWindowName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMMaintenanceWindow [-InputObject] <IResultObject> [-DisableWildcardHandling] [-Force] [-ForceWildcardHandling] -MaintenanceWindowName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
