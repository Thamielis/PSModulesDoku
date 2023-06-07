Set-CMDiscoveryMethod
---------------------




### Synopsis
Changes configuration settings of a discovery method.



---


### Description

The Set-CMDiscoveryMethod cmdlet changes configuration settings of a discovery method. Discovery identifies computer and user resources that Configuration Manager can manage. When Configuration Manager discovers a resource, Configuration Manager creates a record in the Configuration Manager database for the resource and its associated information. You can then use the discovery information to help you to install the Configuration Manager client and create custom queries and collections to logically group resources for related management tasks.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDiscoveryMethod](Get-CMDiscoveryMethod)



* [New-CMSchedule](New-CMSchedule)





---


### Examples
#### Example 1: Modify network discovery
```PowerShell
PS XYZ:\> Set-CMDiscoveryMethod -NetworkDiscovery -SiteCode "CM4" -Enabled $True -NetworkDiscoveryType ToplogyAndClient -SlowNetworkSpeed $True
```
This command modifies network discovery for the site that has the site code CM4. The command specifies topology and client network discovery and the slow network speed option. The command also enables discovery.
#### Example 2: Modify Active Directory system discovery
```PowerShell
PS XYZ:\> $Schedule = New-CMSchedule -RecurInterval Minutes -Start "2012/10/20 00:00:00" -End "2013/10/20 00:00:00" -RecurCount 10
PS XYZ:\> Set-CMDiscoveryMethod -ActiveDirectorySystemDiscovery -SiteCode "CM4" -AddAdditionalAttribute "331", "431", "134" -DeltaDiscoveryIntervalMinutes 8 -Enabled $True -EnableDeltaDiscovery $True -EnableFilteringExpiredLogon $True -PollingSchedule $Schedule -RemoveAdditionalAttribute "123","cn" -TimeSinceLastLogonDays 80
```
The first command creates a schedule object by using the New-CMSchedule cmdlet and stores it in the $Schedule variable.


The second command enables the computer discovery for the site that has the site code CM4. The command specifies the schedule object stored in the $Schedule variable as the polling schedule and enables delta discovery to find new and modified computers since the last discovery. The command specifies that delta discovery takes place every 8 minutes.


The second command also limits the computers found to those that a user has logged onto in the last 80 days. Also, the command adds and removes specified attributes from the attributes used to limit computers.
#### Example 3: Modify forest discovery
```PowerShell
PS XYZ:\> $Schedule = New-CMSchedule -RecurInterval Minutes -Start "2012/10/20 00:00:00" -End "2013/10/20 00:00:00" -RecurCount 10
PS XYZ:\> Set-CMDiscoveryMethod -ActiveDirectoryForestDiscovery -SiteCode "CM4" -EnableActiveDirectorySiteBoundaryCreation $True -Enabled $True  -EnableSubnetBoundaryCreation $True -PollingSchedule $Schedule
```
The first command creates a schedule object by using the New-CMSchedule cmdlet, and then stores it in the $Schedule variable.


The second command enables this discovery site that has the site code CM4. The command specifies the schedule object stored in the $Schedule variable as the polling interval and enables Active Directory boundary creation and subnet boundary creation.
#### Example 4: Enable heartbeat discovery
```PowerShell
PS XYZ:\> $Schedule = New-CMSchedule -RecurInterval Minutes -Start "2012/10/20 00:00:00" -End "2013/10/20 00:00:00" -RecurCount 10
PS XYZ:\> Set-CMDiscoveryMethod -Heartbeat -SiteCode "CM4" -Enabled $True -PollingSchedule $Schedule
```
The first command creates a schedule object by using the New-CMSchedule cmdlet and stores it in the $Schedule variable.


The second command enables heartbeat discovery and specifies the object stored in the $Schedule variable as the polling schedule for the site that has the site code CM4.


---


### Parameters
#### **ActiveDirectoryContainer**

Specifies an array of names of Active Directory containers.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **ActiveDirectoryForestDiscovery**

Indicates that the discovery method discovers security groups, including local, global, and universal groups from specified locations in Active Directory Domain Services (AD DS).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ActiveDirectoryGroupDiscovery**

Indicates that the discovery method discovers additional information, including the computer organizational unit (OU) and group membership, about previously discovered computers from specified locations in AD DS.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ActiveDirectorySystemDiscovery**

Indicates that the discovery method discovers computers from specified locations in AD DS.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ActiveDirectoryUserDiscovery**

Indicates that the discovery method discovers users from specified locations in AD DS.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **AddActiveDirectoryContainer**








|Type        |Required|Position|PipelineInput|Aliases                     |
|------------|--------|--------|-------------|----------------------------|
|`[String[]]`|false   |named   |False        |AddActiveDirectoryContainers|



#### **AddAdditionalAttribute**

Specifies an array of Active Directory object attributes. The cmdlet adds these attributes to the list of attributes that Configuration Manager discovers.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **AddGroupDiscoveryScope**








|Type                       |Required|Position|PipelineInput|
|---------------------------|--------|--------|-------------|
|`[ADGroupDiscoveryScope[]]`|false   |named   |False        |



#### **ClearActiveDirectoryContainer**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DeltaDiscoveryMins**








|Type     |Required|Position|PipelineInput|Aliases                                                     |
|---------|--------|--------|-------------|------------------------------------------------------------|
|`[Int32]`|false   |named   |False        |DeltaDiscoveryIntervalMinutes<br/>DeltaDiscoveryIntervalMins|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DiscoverDistributionGroupMembership**








|Type       |Required|Position|PipelineInput|Aliases                             |
|-----------|--------|--------|-------------|------------------------------------|
|`[Boolean]`|false   |named   |False        |DiscoverDistributionGroupsMembership|



#### **EnableActiveDirectorySiteBoundaryCreation**

Indicates whether Configuration Manager creates Active Directory boundaries from AD DS discovery information.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Enabled**

Indicates whether to enable the Configuration Manager discovery. If you specify a value of $False, Configuration Manager does not discover resources by using this discovery.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableDeltaDiscovery**

Indicates whether Configuration Manager discovers resources created or modified in AD DS since the last discovery cycle. If you specify a value of $True for this parameter, specify a value for the DeltaDiscoveryIntervalMinutes parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableFilteringExpiredLogon**

Indicates whether Configuration Manager discovers only computers that have logged onto a domain within a specified number of days. Specify the number of days by using the TimeSinceLastLogonDays parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableFilteringExpiredPassword**

Indicates whether Configuration Manager discovers only computers that have updated their computer account password within a specified number of days. Specify the number of days by using the TimeSinceLastPasswordUpdateDays parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableIncludeGroup**

{{ Fill EnableIncludeGroup Description }}






|Type       |Required|Position|PipelineInput|Aliases            |
|-----------|--------|--------|-------------|-------------------|
|`[Boolean]`|false   |named   |False        |EnableIncludeGroups|



#### **EnableRecursive**

{{ Fill EnableRecursive Description }}






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSubnetBoundaryCreation**

Indicates whether Configuration Manager creates IP address range boundaries from AD DS discovery information.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Heartbeat**

Indicates that the discovery method updates discovery records for Configuration Manager clients in the Configuration Manager database without discovering new resources.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **IncludeGroup**








|Type      |Required|Position|PipelineInput|Aliases      |
|----------|--------|--------|-------------|-------------|
|`[Switch]`|false   |named   |False        |IncludeGroups|



#### **NetworkDiscovery**

Indicates that the discovery method searches the network infrastructure for network devices, such as printers, routers, and bridges, that have IP addresses.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **NetworkDiscoveryType**

Specifies the network discovery type. If you specify the NetworkDiscovery parameter, specify one of the following types:


* ToplogyAndClient. The discovery finds the topology of your network and potential client devices. - ToplogyClientAndClientOperatingSystem. The discovery finds the topology of your network. The discovery finds potential client devices and their operating systems and versions. - Topology. The discovery finds the topology of your network by discovering IP subnets and routers.



Valid Values:

* Topology
* TopologyAndClient
* TopologyAndClient
* TopologyClientAndClientOperatingSystem
* TopologyClientAndClientOperatingSystem






|Type                    |Required|Position|PipelineInput|
|------------------------|--------|--------|-------------|
|`[NetworkDiscoveryType]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PollingSchedule**

Specifies a schedule object. To obtain a schedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet. The polling schedule determines how often Configuration Manager attempts to discover groups, systems, or user data.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **Recursive**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveActiveDirectoryContainer**








|Type        |Required|Position|PipelineInput|Aliases                        |
|------------|--------|--------|-------------|-------------------------------|
|`[String[]]`|false   |named   |False        |RemoveActiveDirectoryContainers|



#### **RemoveAdditionalAttribute**

Specifies an array of Active Directory object attributes. The cmdlet removes these attributes from the list of attributes that Configuration Manager discovers.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **RemoveGroupDiscoveryScope**








|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **SiteCode**

Specifies the site code for a Configuration Manager site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SlowNetworkSpeed**

Indicates whether Configuration Manager makes adjustments to its discovery settings for networks that have low bandwidth.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **TimeSinceLastLogonDays**

Specifies the number of days since the last logon when the EnableFilteringExpiredLogon parameter had a value of $True.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TimeSinceLastPasswordUpdateDays**

Specifies the number of days since that last password updated when the EnableFilteringExpiredPassword parameter had a value of $True.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UserName**

{{ Fill UserName Description }}






|Type      |Required|Position|PipelineInput|Aliases                 |
|----------|--------|--------|-------------|------------------------|
|`[String]`|false   |named   |False        |DiscoveryAccountUserName|



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
Set-CMDiscoveryMethod [-ActiveDirectoryContainer <String[]>] -ActiveDirectorySystemDiscovery [-AddActiveDirectoryContainer <String[]>] [-AddAdditionalAttribute <String[]>] [-ClearActiveDirectoryContainer] [-DeltaDiscoveryMins <Int32>] [-DisableWildcardHandling] [-Enabled <Boolean>] [-EnableDeltaDiscovery <Boolean>] [-EnableFilteringExpiredLogon <Boolean>] [-EnableFilteringExpiredPassword <Boolean>] [-EnableIncludeGroup <Boolean>] [-EnableRecursive <Boolean>] [-ForceWildcardHandling] [-IncludeGroup] [-PassThru] [-PollingSchedule <IResultObject>] [-Recursive] [-RemoveActiveDirectoryContainer <String[]>] [-RemoveAdditionalAttribute <String[]>] [-SiteCode <String>] [-TimeSinceLastLogonDays <Int32>] [-TimeSinceLastPasswordUpdateDays <Int32>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDiscoveryMethod [-ActiveDirectoryContainer <String[]>] -ActiveDirectoryUserDiscovery [-AddActiveDirectoryContainer <String[]>] [-AddAdditionalAttribute <String[]>] [-ClearActiveDirectoryContainer] [-DeltaDiscoveryMins <Int32>] [-DisableWildcardHandling] [-Enabled <Boolean>] [-EnableDeltaDiscovery <Boolean>] [-EnableIncludeGroup <Boolean>] [-EnableRecursive <Boolean>] [-ForceWildcardHandling] [-IncludeGroup] [-PassThru] [-PollingSchedule <IResultObject>] [-Recursive] [-RemoveActiveDirectoryContainer <String[]>] [-RemoveAdditionalAttribute <String[]>] [-SiteCode <String>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDiscoveryMethod -ActiveDirectoryForestDiscovery [-DisableWildcardHandling] [-EnableActiveDirectorySiteBoundaryCreation <Boolean>] [-Enabled <Boolean>] [-EnableSubnetBoundaryCreation <Boolean>] [-ForceWildcardHandling] [-PassThru] [-PollingSchedule <IResultObject>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDiscoveryMethod -ActiveDirectoryGroupDiscovery [-AddGroupDiscoveryScope <ADGroupDiscoveryScope[]>] [-ClearActiveDirectoryContainer] [-DeltaDiscoveryMins <Int32>] [-DisableWildcardHandling] [-DiscoverDistributionGroupMembership <Boolean>] [-Enabled <Boolean>] [-EnableDeltaDiscovery <Boolean>] [-EnableFilteringExpiredLogon <Boolean>] [-EnableFilteringExpiredPassword <Boolean>] [-ForceWildcardHandling] [-PassThru] [-PollingSchedule <IResultObject>] [-RemoveGroupDiscoveryScope <String[]>] [-SiteCode <String>] [-TimeSinceLastLogonDays <Int32>] [-TimeSinceLastPasswordUpdateDays <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDiscoveryMethod [-DisableWildcardHandling] [-Enabled <Boolean>] [-ForceWildcardHandling] -Heartbeat [-PassThru] [-PollingSchedule <IResultObject>] [-SiteCode <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDiscoveryMethod [-DisableWildcardHandling] [-Enabled <Boolean>] [-ForceWildcardHandling] -NetworkDiscovery [-NetworkDiscoveryType {Topology | TopologyAndClient | ToplogyAndClient | TopologyClientAndClientOperatingSystem | ToplogyClientAndClientOperatingSystem}] [-PassThru] [-SiteCode <String>] [-SlowNetworkSpeed <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
