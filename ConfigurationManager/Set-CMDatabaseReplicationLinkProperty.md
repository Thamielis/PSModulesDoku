Set-CMDatabaseReplicationLinkProperty
-------------------------------------




### Synopsis
Changes configuration settings for a database replication link.



---


### Description

The Set-CMDatabaseReplicationLinkProperty cmdlet changes configuration settings for a database replication link between a Configuration Manager parent site and child site.



Database replication for Configuration Manager sites transfers data and merges changes made in a site database with information stored at other sites in the Configuration Manager hierarchy. This enables all sites to share the same information.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDatabaseReplicationLinkProperty](Get-CMDatabaseReplicationLinkProperty)



* [Get-CMDataBaseReplicationStatus](Get-CMDataBaseReplicationStatus)





---


### Examples
#### Example 1: Change settings of a database replication link
```PowerShell
PS XYZ:\> Set-CMDatabaseReplicationLinkProperty -ParentSiteCode "CCC" -ChildSiteCode "CCB" -EnableDistributedViewForHardwareInventory 1 -EnableDistributedViewForSoftwareInventory 1 -EnableDistributedViewForStatusMessage 1 -ReplicationDataTrafficSummarizationIntervalMinutes 12 -DegradedLinkStatusRetryCount 40 -FailedLinkStatusRetryCount 60 -GenerateReplicationDownAlert 1 -ReplicationDownAlertThresholdMinutes 20
```
This command changes configuration settings for a database replication link between the Configuration Manager parent site that has the site code CCC and the child site that has the site code CCB.
#### Example 2: Set the schedule for a database replication link
```PowerShell
PS XYZ:\> Set-CMDatabaseReplicationLinkProperty -ParentSiteCode "CCC" -ChildSiteCode "CCB" -DaysOfWeek Friday, Monday, Tuesday -TimePeriodStart 8 -TimePeriodEnd 0 -AvailabilityLevel HINVSINV
```
This command sets the schedule for the database replication link between the Configuration Manager parent site that has the site code CCC and the child site that has the site code CCB. The command specifies that Configuration Manager replicates the database for Configuration Manager sites on Friday, Monday, and Tuesday. The command specifies software and hardware inventory availability on the client computer.


---


### Parameters
#### **AvailabilityLevel**

Specifies the availability level for software and hardware inventory on a client computer. The acceptable values for this parameter are:


* Closed


* HINV


* SINV


* HINVSINV


* StatMSG


* HINVStatMSG


* SINVStatMSG


* HINVSINVStatMSG



Valid Values:

* Closed
* HINV
* SINV
* HINVSINV
* StatMSG
* HINVStatMSG
* SINVStatMSG
* HINVSINVStatMSG






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[InvAvailabilityLevel]`|true    |named   |False        |



#### **ChildSiteCode**

Specifies a site code for a Configuration Manager site. This parameter refers to the child site.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Site2  |



#### **DaysOfWeek**

Specifies an array of day names that determine the days of each week on which Configuration Manager replicates the database for Configuration Manager sites. The acceptable values for this parameter are:


* Monday


* Tuesday


* Wednesday


* Thursday


* Friday


* Saturday


* Sunday



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
|`[DaysOfWeek[]]`|true    |named   |False        |



#### **DegradedLinkStatusRetryCount**

Specifies a retry count when a replication group or object is delayed due to degraded link status.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableDistributedViewForHardwareInventory**

Indicates whether Configuration Manager configures the SQL Server distributed partitioned views for hardware inventory.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableDistributedViewForSoftwareInventory**

Indicates whether Configuration Manager configures the SQL Server distributed partitioned views for software inventory.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableDistributedViewForStatusMessage**

Indicates whether Configuration Manager configures the SQL Server distributed partitioned views for status messages.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **FailedLinkStatusRetryCount**

Specifies a retry count when a replication group or object is delayed by failed link status.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GenerateReplicationDownAlert**

Indicates whether to generate a replication down alert.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ParentSiteCode**

Specifies a site code for a Configuration Manager site. This parameter refers to the parent site.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Site1  |



#### **ReplicationDataTrafficSummarizationMins**








|Type     |Required|Position|PipelineInput|Aliases                                           |
|---------|--------|--------|-------------|--------------------------------------------------|
|`[Int32]`|false   |named   |False        |ReplicationDataTrafficSummarizationIntervalMinutes|



#### **ReplicationDownAlertMins**








|Type     |Required|Position|PipelineInput|Aliases                             |
|---------|--------|--------|-------------|------------------------------------|
|`[Int32]`|false   |named   |False        |ReplicationDownAlertThresholdMinutes|



#### **ReplicationEndHr**








|Type     |Required|Position|PipelineInput|Aliases                             |
|---------|--------|--------|-------------|------------------------------------|
|`[Int32]`|true    |named   |False        |TimePeriodEnd<br/>ReplicationEndHour|



#### **ReplicationStartHr**








|Type     |Required|Position|PipelineInput|Aliases                                 |
|---------|--------|--------|-------------|----------------------------------------|
|`[Int32]`|true    |named   |False        |TimePeriodStart<br/>ReplicationStartHour|



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
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMDatabaseReplicationLinkProperty -AvailabilityLevel {Closed | HINV | SINV | HINVSINV | StatMSG | HINVStatMSG | SINVStatMSG | HINVSINVStatMSG} -ChildSiteCode <String> -DaysOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday} [-DisableWildcardHandling] [-ForceWildcardHandling] -ParentSiteCode <String> -ReplicationEndHr <Int32> -ReplicationStartHr <Int32> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDatabaseReplicationLinkProperty -ChildSiteCode <String> [-DegradedLinkStatusRetryCount <Int32>] [-DisableWildcardHandling] [-EnableDistributedViewForHardwareInventory <Boolean>] [-EnableDistributedViewForSoftwareInventory <Boolean>] [-EnableDistributedViewForStatusMessage <Boolean>] [-FailedLinkStatusRetryCount <Int32>] [-ForceWildcardHandling] [-GenerateReplicationDownAlert <Boolean>] -ParentSiteCode <String> [-ReplicationDataTrafficSummarizationMins <Int32>] [-ReplicationDownAlertMins <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
