New-CMMaintenanceWindow
-----------------------




### Synopsis
Create a maintenance window for a collection.



---


### Description

Use this cmdlet to create a maintenance window for a collection. Maintenance windows are recurring periods of time when the Configuration Manager client can run tasks. For example, apply software updates or install software. This window makes sure that significant system changes only happen at times that don't affect productivity and uptime.



For more information on maintenance windows, see How to use maintenance windows in Configuration Manager (/mem/configmgr/core/clients/manage/collections/use-maintenance-windows).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMMaintenanceWindow](Get-CMMaintenanceWindow)



* [Remove-CMMaintenanceWindow](Remove-CMMaintenanceWindow)



* [Set-CMMaintenanceWindow](Set-CMMaintenanceWindow)



* [Convert-CMSchedule](Convert-CMSchedule)



* [New-CMSchedule](New-CMSchedule)



* [How to use maintenance windows in Configuration Manager](How to use maintenance windows in Configuration Manager)





---


### Examples
#### Example 1: Create a maintenance window
```PowerShell
$MWSchedule = New-CMSchedule -DayOfWeek Friday -DurationCount 1 -DurationInterval Hours -RecurCount 1 -Start "10/12/2013 21:00:00"
New-CMMaintenanceWindow -CollectionId "XYZ0005D" -Name "MonthlySchedule" -Schedule $MWSchedule
```

#### Example 2: Copy a maintenance window between collections
```PowerShell
$mw1 = Get-CMMaintenanceWindow -CollectionId "XYZ0003F" -MaintenanceWindowName "nightly SUM window"
New-CMMaintenanceWindow -CollectionId "XYZ0005D" -Name $mw1.Name -Schedule (Convert-CMSchedule -ScheduleString $mw1.ServiceWindowSchedules) -ApplyTo SoftwareUpdatesOnly
```



---


### Parameters
#### **ApplyTo**

Specify the type of maintenance window to create:


* `Any`: The maintenance window applies to all deployments.


* `SoftwareUpdatesOnly`: The maintenance window only applies to software update deployments.


* `TaskSequencesOnly`: The maintenance window only applies to task sequence deployments.




If you don't specify this parameter, `Any` is the default.




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

Specify the ID of a collection to add the maintenance window. This ID is a standard collection ID, for example `XYZ0003F`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **CollectionName**

Specify the name of a collection to add the maintenance window.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



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

Specify an object for a collection to add the maintenance window. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|Collection<br/>Site|



#### **IsEnabled**

To create a maintenance window on a collection, but not have it active, set this parameter to `$false`. If you don't include this parameter, this cmdlet enables the maintenance window.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **IsUtc**

To configure the maintenance window schedule to use Coordinated Universal Time (UTC), set this parameter to `$true`. If you don't include this parameter, the schedule uses local time.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Name**

Specify the name of the maintenance window.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|true    |named   |False        |MaintenanceWindowName|



#### **Schedule**

Specify a schedule object for when the maintenance window occurs. To get this object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.


The maintenance window object stores the schedule as a token string. To copy a schedule from another object, use the Convert-CMSchedule (Convert-CMSchedule.md)cmdlet. For example, `Convert-CMSchedule -ScheduleString $mw1.ServiceWindowSchedules`.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



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
* IResultObject#SMS_ServiceWindow






---


### Notes
For more information on this return object and its properties, see SMS_ServiceWindow server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_servicewindow-server-wmi-class).



---


### Syntax
```PowerShell
New-CMMaintenanceWindow [-CollectionId] <String> [-ApplyTo {Any | SoftwareUpdatesOnly | TaskSequencesOnly}] [-ApplyToSoftwareUpdateOnly] [-ApplyToTaskSequenceOnly] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsEnabled <Boolean>] [-IsUtc <Boolean>] -Name <String> -Schedule <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMMaintenanceWindow [-CollectionName] <String> [-ApplyTo {Any | SoftwareUpdatesOnly | TaskSequencesOnly}] [-ApplyToSoftwareUpdateOnly] [-ApplyToTaskSequenceOnly] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsEnabled <Boolean>] [-IsUtc <Boolean>] -Name <String> -Schedule <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMMaintenanceWindow [-InputObject] <IResultObject> [-ApplyTo {Any | SoftwareUpdatesOnly | TaskSequencesOnly}] [-ApplyToSoftwareUpdateOnly] [-ApplyToTaskSequenceOnly] [-DisableWildcardHandling] [-ForceWildcardHandling] [-IsEnabled <Boolean>] [-IsUtc <Boolean>] -Name <String> -Schedule <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
