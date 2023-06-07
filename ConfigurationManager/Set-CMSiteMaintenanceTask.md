Set-CMSiteMaintenanceTask
-------------------------




### Synopsis
Change settings for a Configuration Manager maintenance task.



---


### Description

The Set-CMSiteMaintenanceTask cmdlet changes settings for a Configuration Manager maintenance task. For more information, see Maintenance tasks (/mem/configmgr/core/servers/manage/maintenance-tasks).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSiteMaintenanceTask](Get-CMSiteMaintenanceTask)





---


### Examples
#### Example 1: Set a maintenance task to run once a week
```PowerShell
Set-CMSiteMaintenanceTask -SiteCode "CM1" -MaintenanceTaskName "Backup SMS Site Server" -DaysOfWeek Friday
```

#### Example 2: Configure backup destinations
```PowerShell
Set-CMSiteMaintenanceTask -Name $TaskName -SiteBackupPath "c:\site-backup" -SqlBackupPath "c:\sql-backup" -BeginTime (Get-Date) -DaysOfWeek Sunday,Monday -EnableAlert $true -Enabled $true
```



---


### Parameters
#### **BeginTime**

Specify the date and time at which a maintenance task starts.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **DaysOfWeek**

Specify an array of day names that determine the days of each week on which the maintenance task runs.



Valid Values:

* Sunday
* Monday
* Tuesday
* Wednesday
* Thursday
* Friday
* Saturday






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[DaysOfWeek[]]`|false   |named   |False        |



#### **DeleteOlderThanDays**

For maintenance tasks that delete aged data, use this parameter to specify the number of days.






|Type     |Required|Position|PipelineInput|Aliases                                |
|---------|--------|--------|-------------|---------------------------------------|
|`[Int32]`|false   |named   |False        |DeleteOlderThan<br/>DeleteThanOlderDays|



#### **DeviceName**

Specifies the name of the device on which the maintenance task runs.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAlert**

Set this parameter to `$true` to enable alerts for task failures, if the task supports it.






|Type       |Required|Position|PipelineInput|Aliases     |
|-----------|--------|--------|-------------|------------|
|`[Boolean]`|false   |named   |False        |EnabledAlert|



#### **Enabled**

Indicates whether the maintenance task is enabled in Configuration Manager.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **FixedRun**

Indicates that this cmdlet modifies the maintenance task as a fixed run.






|Type      |Required|Position|PipelineInput|Aliases                                     |
|----------|--------|--------|-------------|--------------------------------------------|
|`[Switch]`|false   |named   |False        |FixedRunInterval<br/>DisableFixedRunInterval|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify the maintenance task object to configure. To get this object, use the Get-CMSiteMaintenanceTask (Get-CMSiteMaintenanceTask.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases              |
|-----------------|--------|--------|--------------|---------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|MaintenanceTaskObject|



#### **LatestBeginTime**

Specifies a future date and time at which the maintenance task runs.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **MaintenanceTask**

Specify the name of a maintenance task to configure.



Valid Values:

* BackupSiteServer
* CheckApplicationTitleWithInventoryInformation
* ClearUndiscoveredClients
* DeleteAgedApplicationRequestData
* DeleteUnusedApplicationRevisions
* DeleteAgedClientOperations
* DeleteAgedCollectedFiles
* DeleteAgedComputerAssociationData
* DeleteAgedDeleteDetectionData
* DeleteAgedDeviceWipeRecord
* DeleteAgedDiscoveryData
* DeleteAgedEnrolledDevices
* DeleteAgedEndpointProtectionHealthStatusHistoryData
* DeleteAgedDevicesManagedByTheExchangeServerConnector
* DeleteAgedInventoryHistory
* DeleteAgedLogData
* DeleteAgedSoftwareMeteringData
* DeleteAgedSoftwareMeteringSummaryData
* DeleteAgedClientPresenceHistory
* DeleteAgedNotificationTaskHistory
* DeleteAgedReplicationTrackingData
* DeleteAgedReplicationSummaryData
* DeleteAgedStatusMessages
* DeleteAgedThreatData
* DeleteAgedUnknownComputers
* DeleteAgedUserDeviceAffinityData
* DeleteInactiveClientDiscoveryData
* DeleteObsoleteAlerts
* DeleteObsoleteClientDiscoveryData
* DeleteObsoleteForestDiscoverySitesAndSubnets
* EvaluateProvisionedAmtComputerCertificates
* MonitorKeys
* RebuildIndexes
* SummarizeSoftwareMeteringFileUsageData
* SummarizeInstalledSoftwareData
* SummarizeSoftwareMeteringMonthlyUsageData
* DeleteAgedDistributionPointUsageStats
* DeleteAgedProxyTrafficData






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[MaintenanceTask]`|true    |named   |False        |



#### **Name**

Specify the name of a maintenance task object to configure.






|Type      |Required|Position|PipelineInput|Aliases                                      |
|----------|--------|--------|-------------|---------------------------------------------|
|`[String]`|true    |named   |False        |MaintenanceTaskName<br/>TaskName<br/>ItemName|



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RunIntervalMins**








|Type     |Required|Position|PipelineInput|Aliases           |
|---------|--------|--------|-------------|------------------|
|`[Int32]`|false   |named   |False        |RunIntervalMinutes|



#### **RunNow**

Add this parameter to have Configuration Manager run the maintenance task immediately.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **SiteBackupPath**

Applies to version 2010 and later. For the Backup Site Server task, specify the Site backup destination . The site server computer account needs full control to the destination folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code of the Configuration Manager site that hosts the site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SqlBackupPath**

Applies to version 2010 and later. For the Backup Site Server task, specify the SQL backup destination . The site server computer account needs full control to the destination folder.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SummaryTask**

Specifies a summary maintenance task.






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[SummaryTask]`|true    |named   |False        |



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
* IResultObject#SMS_SCI_SQLTask






---


### Notes




---


### Syntax
```PowerShell
Set-CMSiteMaintenanceTask [-BeginTime <DateTime>] [-DaysOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday}] [-DeleteOlderThanDays <Int32>] [-DeviceName <String>] [-DisableWildcardHandling] [-EnableAlert <Boolean>] [-Enabled <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-LatestBeginTime <DateTime>] [-PassThru] [-SiteBackupPath <String>] [-SiteCode <String>] [-SqlBackupPath <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSiteMaintenanceTask [-BeginTime <DateTime>] [-DaysOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday}] [-DeleteOlderThanDays <Int32>] [-DeviceName <String>] [-DisableWildcardHandling] [-EnableAlert <Boolean>] [-Enabled <Boolean>] [-ForceWildcardHandling] [-LatestBeginTime <DateTime>] -Name <String> [-PassThru] [-SiteBackupPath <String>] [-SiteCode <String>] [-SqlBackupPath <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSiteMaintenanceTask [-BeginTime <DateTime>] [-DaysOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday}] [-DeleteOlderThanDays <Int32>] [-DeviceName <String>] [-DisableWildcardHandling] [-EnableAlert <Boolean>] [-Enabled <Boolean>] [-ForceWildcardHandling] [-LatestBeginTime <DateTime>] -MaintenanceTask {BackupSiteServer | CheckApplicationTitleWithInventoryInformation | ClearUndiscoveredClients | DeleteAgedApplicationRequestData | DeleteUnusedApplicationRevisions | DeleteAgedClientOperations | DeleteAgedCollectedFiles | DeleteAgedComputerAssociationData | DeleteAgedDeleteDetectionData | DeleteAgedDeviceWipeRecord | DeleteAgedDiscoveryData | DeleteAgedEnrolledDevices | DeleteAgedEndpointProtectionHealthStatusHistoryData | DeleteAgedDevicesManagedByTheExchangeServerConnector | DeleteAgedInventoryHistory | DeleteAgedLogData | DeleteAgedSoftwareMeteringData | DeleteAgedSoftwareMeteringSummaryData | DeleteAgedClientPresenceHistory | DeleteAgedNotificationTaskHistory | DeleteAgedReplicationTrackingData | DeleteAgedReplicationSummaryData | DeleteAgedStatusMessages | DeleteAgedThreatData | DeleteAgedUnknownComputers | DeleteAgedUserDeviceAffinityData | DeleteInactiveClientDiscoveryData | DeleteObsoleteAlerts | DeleteObsoleteClientDiscoveryData | DeleteObsoleteForestDiscoverySitesAndSubnets | EvaluateProvisionedAmtComputerCertificates | MonitorKeys | RebuildIndexes | SummarizeSoftwareMeteringFileUsageData | SummarizeInstalledSoftwareData | SummarizeSoftwareMeteringMonthlyUsageData | DeleteAgedDistributionPointUsageStats | DeleteAgedProxyTrafficData} [-PassThru] [-SiteBackupPath <String>] [-SiteCode <String>] [-SqlBackupPath <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSiteMaintenanceTask [-DisableWildcardHandling] [-FixedRun] [-ForceWildcardHandling] [-PassThru] [-RunIntervalMins <Int32>] [-RunNow] [-SiteCode <String>] -SummaryTask {UpdateApplicationCatalogTables} [-Confirm] [-WhatIf] [<CommonParameters>]
```
