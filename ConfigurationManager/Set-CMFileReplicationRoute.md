Set-CMFileReplicationRoute
--------------------------




### Synopsis
Changes settings for a file replication route in Configuration Manager.



---


### Description

The Set-CMFileReplicationRoute cmdlet changes settings for a file replication route from Configuration Manager. Configuration Manager uses file replication routes to transfer file-based data between sites in a hierarchy. Each file replication route identifies a destination site to which file-based data can transfer.



File replication routes were known as addresses in versions of Configuration Manager before Configuration Manager. The functionality of file replication routes is the same as that of addresses in earlier versions.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMFileReplicationRoute](Get-CMFileReplicationRoute)



* [New-CMFileReplicationRoute](New-CMFileReplicationRoute)



* [Remove-CMFileReplicationRoute](Remove-CMFileReplicationRoute)





---


### Examples
#### Example 1: Specify a file replication route by using a replication account name
```PowerShell
PS XYZ:\> Set-CMFileReplicationRoute -SourceSiteCode "CM2" -DestinationSiteCode "SS2" -FileReplicationAccountName "11\12" -Unlimited
```
This command specifies a file replication route between the source site named CM2 and the destination site named SS2. It uses the user account name 11\12 for file replication.
#### Example 2: Specify a file replication route by using a source and destination site names
```PowerShell
PS XYZ:\> Set-CMFileReplicationRoute -SourceSiteCode "CM2" -DestinationSiteCode "SS2" -ControlNetworkLoadSchedule -DaysOfWeek Friday, Sunday -AvailabilityLevel All
```
This command specifies a file replication route between the source site named CM2 and the destination site named SS2. It schedules file replication for Fridays and Sundays.


---


### Parameters
#### **AvailabilityLevel**

Specifies a value that indicates the priorities for which the scheduled restriction allows. The system allows all priorities, no priorities, high priority only or high and medium priority. The acceptable values for this parameter are:


* All


* Closed


* High


* MediumHigh



Valid Values:

* All
* MediumHigh
* High
* Closed






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[AvailabilityLevel]`|false   |named   |False        |



#### **BeginHr**








|Type     |Required|Position|PipelineInput|Aliases                      |
|---------|--------|--------|-------------|-----------------------------|
|`[Int32]`|false   |named   |False        |TimePeriodStart<br/>BeginHour|



#### **ControlNetworkLoadSchedule**

Indicates that scheduled replication controls network load.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DataBlockSizeKB**

Specifies a data block size, in kilobytes.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DaysOfWeek**

Specifies an array of values that indicate when the file replication runs for this route. The acceptable values for this parameter are:


* Friday


* Saturday


* Sunday


* Monday


* Tuesday


* Wednesday


* Thursday



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



#### **DelayBetweenDataBlockSec**








|Type     |Required|Position|PipelineInput|Aliases                                                    |
|---------|--------|--------|-------------|-----------------------------------------------------------|
|`[Int32]`|false   |named   |False        |DelayBetweenDataBlocksSeconds<br/>DelayBetweenDataBlocksSec|



#### **DestinationSiteCode**

Specifies the destination site in the file replication route that you change by using a site code.






|Type      |Required|Position|PipelineInput|Aliases                                    |
|----------|--------|--------|-------------|-------------------------------------------|
|`[String]`|true    |named   |False        |DesSiteCode<br/>DestSiteCode<br/>ServerFqdn|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EndHr**








|Type     |Required|Position|PipelineInput|Aliases                  |
|---------|--------|--------|-------------|-------------------------|
|`[Int32]`|false   |named   |False        |TimePeriodEnd<br/>EndHour|



#### **FileReplicationAccountName**

Specifies the account that Configuration Manager uses to install a site on the specified server and maintain communications between the site and other sites. This account must have local administrative credentials.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **LimitAvailableBandwidthPercent**








|Type     |Required|Position|PipelineInput|Aliases                          |
|---------|--------|--------|-------------|---------------------------------|
|`[Int32]`|false   |named   |False        |LimitAvailableBandwidthPercentage|



#### **Limited**

Indicates that bandwidth for a file replication route is limited.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **LimitedBeginHr**








|Type     |Required|Position|PipelineInput|Aliases                                    |
|---------|--------|--------|-------------|-------------------------------------------|
|`[Int32]`|false   |named   |False        |LimitedTimePeriodStart<br/>LimitedBeginHour|



#### **LimitedEndHr**








|Type     |Required|Position|PipelineInput|Aliases                                |
|---------|--------|--------|-------------|---------------------------------------|
|`[Int32]`|false   |named   |False        |LimitedTimePeriodEnd<br/>LimitedEndHour|



#### **PulseMode**

Indicates that file replication uses data block size and delays between transmissions. Use this parameter when you have low network bandwidth between sites.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **SourceSiteCode**

Specifies the source site in the file replication route that you change by using a site code.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteCode|



#### **Unlimited**

Indicates that bandwidth for a file replication route is unlimited.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



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
* 






---


### Notes




---


### Syntax
```PowerShell
Set-CMFileReplicationRoute [-AvailabilityLevel {All | MediumHigh | High | Closed}] [-BeginHr <Int32>] -ControlNetworkLoadSchedule [-DaysOfWeek {Sunday | Monday | Tuesday | Wednesday | Thursday | Friday | Saturday}] -DestinationSiteCode <String> [-DisableWildcardHandling] [-EndHr <Int32>] [-ForceWildcardHandling] -SourceSiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMFileReplicationRoute [-DataBlockSizeKB <Int32>] [-DelayBetweenDataBlockSec <Int32>] -DestinationSiteCode <String> [-DisableWildcardHandling] [-FileReplicationAccountName <String>] [-ForceWildcardHandling] -PulseMode -SourceSiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMFileReplicationRoute -DestinationSiteCode <String> [-DisableWildcardHandling] [-FileReplicationAccountName <String>] [-ForceWildcardHandling] -SourceSiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMFileReplicationRoute -DestinationSiteCode <String> [-DisableWildcardHandling] [-FileReplicationAccountName <String>] [-ForceWildcardHandling] -SourceSiteCode <String> -Unlimited [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMFileReplicationRoute -DestinationSiteCode <String> [-DisableWildcardHandling] [-FileReplicationAccountName <String>] [-ForceWildcardHandling] [-LimitAvailableBandwidthPercent <Int32>] -Limited [-LimitedBeginHr <Int32>] [-LimitedEndHr <Int32>] -SourceSiteCode <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
