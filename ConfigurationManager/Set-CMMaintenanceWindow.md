Set-CMMaintenanceWindow
-----------------------




### Synopsis
Modify a maintenance window.



---


### Description

Use this cmdlet to configure a maintenance window on a collection.



For more information on maintenance windows, see How to use maintenance windows in Configuration Manager (/mem/configmgr/core/clients/manage/collections/use-maintenance-windows).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMMaintenanceWindow](Get-CMMaintenanceWindow)



* [New-CMMaintenanceWindow](New-CMMaintenanceWindow)



* [Remove-CMMaintenanceWindow](Remove-CMMaintenanceWindow)



* [Convert-CMSchedule](Convert-CMSchedule)



* [New-CMSchedule](New-CMSchedule)



* [How to use maintenance windows in Configuration Manager](How to use maintenance windows in Configuration Manager)





---


### Examples
#### Example 1: Modify a maintenance window to only apply to task sequence deployments
```PowerShell
Set-CMMaintenanceWindow -Name "DiskCleanup" -CollectionID "XYZ0004D" -ApplyTo TaskSequencesOnly
```



---


### Parameters
#### **ApplyTo**

Specify the type of maintenance window:


* `Any`: The maintenance window applies to all deployments.


* `SoftwareUpdatesOnly`: The maintenance window only applies to software update deployments.


* `TaskSequencesOnly`: The maintenance window only applies to task sequence deployments.



Valid Values:

* Any
* SoftwareUpdatesOnly
* TaskSequencesOnly






|Type                        |Required|Position|PipelineInput|
|----------------------------|--------|--------|-------------|
|`[MaintenanceWindowApplyTo]`|false   |named   |False        |



#### **ApplyToSoftwareUpdateOnly**

This parameter is deprecated. Use the ApplyTo parameter with the SoftwareUpdatesOnly value.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ApplyToTaskSequenceOnly**

This parameter is deprecated. Use the ApplyTo parameter with the TaskSequencesOnly value.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **CollectionId**

Specify the ID of a collection to configure a maintenance window. This ID is a standard collection ID, for example `XYZ0003F`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify the name of a collection to configure a maintenance window.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specify an object for a collection to configure a maintenance window. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection<br/>Site|



#### **IsEnabled**

Use this parameter to configure if the maintenance window is active for the collection:


* `$true`: Enable the maintenance window. Deployments only run during the window's schedule.


* `$false`: Disable the maintenance window. Deployments run at any time as configured.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsUtc**

To configure the maintenance window schedule to use Coordinated Universal Time (UTC), set this parameter to `$true`.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MaintenanceWindow**

Specify an maintenance window object to configure. To get this object, use the Get-CMMaintenanceWindow (Get-CMMaintenanceWindow.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases       |
|-----------------|--------|--------|--------------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|ScheduleWindow|



#### **MaintenanceWindowName**

Specify the name of the maintenance window to configure.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Schedule**

Specify a schedule object for when the maintenance window occurs. To get this object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.


The maintenance window object stores the schedule as a token string. To copy a schedule from another object, use the Convert-CMSchedule (Convert-CMSchedule.md)cmdlet. For example, `Convert-CMSchedule -ScheduleString $mw1.ServiceWindowSchedules`.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



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
Set-CMMaintenanceWindow [-ApplyTo {Any | SoftwareUpdatesOnly | TaskSequencesOnly}] [-ApplyToSoftwareUpdateOnly] [-ApplyToTaskSequenceOnly] -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsEnabled <Boolean>] [-IsUtc <Boolean>] -MaintenanceWindowName <String> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMaintenanceWindow [-ApplyTo {Any | SoftwareUpdatesOnly | TaskSequencesOnly}] [-ApplyToSoftwareUpdateOnly] [-ApplyToTaskSequenceOnly] -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsEnabled <Boolean>] [-IsUtc <Boolean>] -MaintenanceWindow <IResultObject> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMaintenanceWindow [-ApplyTo {Any | SoftwareUpdatesOnly | TaskSequencesOnly}] [-ApplyToSoftwareUpdateOnly] [-ApplyToTaskSequenceOnly] -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsEnabled <Boolean>] [-IsUtc <Boolean>] -MaintenanceWindowName <String> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMaintenanceWindow [-ApplyTo {Any | SoftwareUpdatesOnly | TaskSequencesOnly}] [-ApplyToSoftwareUpdateOnly] [-ApplyToTaskSequenceOnly] -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsEnabled <Boolean>] [-IsUtc <Boolean>] -MaintenanceWindow <IResultObject> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMaintenanceWindow [-ApplyTo {Any | SoftwareUpdatesOnly | TaskSequencesOnly}] [-ApplyToSoftwareUpdateOnly] [-ApplyToTaskSequenceOnly] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsEnabled <Boolean>] [-IsUtc <Boolean>] -MaintenanceWindow <IResultObject> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMMaintenanceWindow [-ApplyTo {Any | SoftwareUpdatesOnly | TaskSequencesOnly}] [-ApplyToSoftwareUpdateOnly] [-ApplyToTaskSequenceOnly] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-IsEnabled <Boolean>] [-IsUtc <Boolean>] -MaintenanceWindowName <String> [-PassThru] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
