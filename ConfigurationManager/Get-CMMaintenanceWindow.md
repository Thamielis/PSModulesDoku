Get-CMMaintenanceWindow
-----------------------




### Synopsis
Get the maintenance windows for a collection.



---


### Description

Use this cmdlet to get the maintenance windows for the specified collection. You can also filter the results to a specific maintenance window.



For more information on maintenance windows, see How to use maintenance windows in Configuration Manager (/mem/configmgr/core/clients/manage/collections/use-maintenance-windows).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMMaintenanceWindow](New-CMMaintenanceWindow)



* [Remove-CMMaintenanceWindow](Remove-CMMaintenanceWindow)



* [Set-CMMaintenanceWindow](Set-CMMaintenanceWindow)



* [How to use maintenance windows in Configuration Manager](How to use maintenance windows in Configuration Manager)





---


### Examples
#### Example 1: Get enabled maintenance windows for a collection by ID
```PowerShell
Get-CMMaintenanceWindow -CollectionID "XYZ0004D" | Where-Object { $_.IsEnabled }
```

#### Example 2: Get all maintenance windows for a collection object
```PowerShell
$coll = Get-CMCollection -CollectionID 'XYZ0003F'
$coll | Get-CMMaintenanceWindow -MaintenanceWindowName 'nightly SUM window'
```

#### Example 3: Get the schedule for a maintenance window
```PowerShell
$mw = Get-CMMaintenanceWindow -CollectionID "XYZ000AB"
Convert-CMSchedule -ScheduleString $mw.ServiceWindowSchedules
```



---


### Parameters
#### **CollectionId**

Specify a collection ID to query for its maintenance windows. This ID is a standard collection ID, for example `XYZ0003F`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



#### **CollectionName**

Specify a collection name to query for its maintenance windows.






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

Specify a collection object to query for its maintenance windows. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases            |
|-----------------|--------|--------|--------------|-------------------|
|`[IResultObject]`|true    |0       |True (ByValue)|Collection<br/>Site|



#### **MaintenanceWindowName**

Specify the name of a maintenance window on the targeted collection. By default, Get-CMMaintenanceWindow returns all maintenance windows. Use this parameter to filter the results to the specified window name.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|false   |named   |False        |Name   |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_ServiceWindow






---


### Notes
For more information on this return object and its properties, see SMS_ServiceWindow server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_servicewindow-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMMaintenanceWindow [-CollectionId] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaintenanceWindowName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMMaintenanceWindow [-CollectionName] <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaintenanceWindowName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMMaintenanceWindow [-InputObject] <IResultObject> [-DisableWildcardHandling] [-ForceWildcardHandling] [-MaintenanceWindowName <String>] [<CommonParameters>]
```
