Set-CMDistributionPoint
-----------------------




### Synopsis
Configure a distribution point.



---


### Description

The Set-CMDistributionPoint cmdlet modifies a distribution point on a site system server.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDistributionPoint](Add-CMDistributionPoint)



* [Get-CMDistributionPoint](Get-CMDistributionPoint)



* [Get-CMSiteSystemServer](Get-CMSiteSystemServer)



* [New-CMSchedule](New-CMSchedule)



* [Remove-CMDistributionPoint](Remove-CMDistributionPoint)



* [Update-CMDistributionPoint](Update-CMDistributionPoint)



* [Install and configure distribution points in Configuration Manager](Install and configure distribution points in Configuration Manager)





---


### Examples
#### Example 1: Set properties of a distribution point
```PowerShell
$DP = Get-CMDistributionPoint -SiteSystemServerName "MySiteSys_11310.Contoso.com"
Set-CMDistributionPoint -InputObject $DP -AllowFallbackForContent $True -AllowPreStaging $True -AllowPxeResponse $False -ClientCommunicationType Http -ClientConnectionType Internet -ContentMonitoringPriority High
```

#### Example 2: Reassign a distribution point to a new site
```PowerShell
Set-CMDistributionPoint -SiteSystemServerName "MyDP.TestDOM.net" -SiteCode "ABC" -ReassignSiteCode "XYZ"
```

#### Example 3: Enable Microsoft Connected Cache
```PowerShell
$dp = Get-CMDistributionPoint -SiteSystemServerName "dp01.contoso.com"

$dp | Set-CMDistributionPoint -RetainDoincCache $true -EnableDoinc $true -AgreeDoincLicense $true

$dp | Set-CMDistributionPoint -LocalDriveDoinc "Z:" -DiskSpaceDoinc 9000 -DiskSpaceUnit GB
```



---


### Parameters
#### **AddBoundaryGroupName**

Adds an array of boundary groups, by name, to a distribution point.






|Type        |Required|Position|PipelineInput|Aliases              |
|------------|--------|--------|-------------|---------------------|
|`[String[]]`|false   |named   |False        |AddBoundaryGroupNames|



#### **AddMacAddressForRespondingPxeRequest**

Adds an array of MAC addresses that respond to PXE requests for a PXE-enabled distribution point.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **AgreeDoincLicense**

When you use the EnableDoinc parameter, set this parameter to `$true` to accept the Microsoft Connected Cache server license terms. For more information, see Microsoft Connected Cache in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache#licensing).


If you've already agreed to the licensing terms, you don't have to include this parameter. You'll see this warning when you unnecessarily include it:<!-- 12502130 --> `The parameter 'AgreeDoincLicense' has been ignored. Reason: Once the license terms agreement is selected, it will be grayed out and never uncheck it.`






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowFallbackForContent**

Indicates whether clients outside of the boundary groups associated with a site system can fall back and use this site system as a source location for content when no other site systems are available.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowPreStaging**

Indicates whether the distribution point is enabled for prestaged content.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowProxyTraffic**

Enables the site system to use a proxy server when it connects to the internet.






|Type       |Required|Position|PipelineInput|Aliases           |
|-----------|--------|--------|-------------|------------------|
|`[Boolean]`|false   |named   |False        |EnableCloudGateway|



#### **AllowPxeResponse**

Indicates whether the distribution point can respond to PXE requests.






|Type       |Required|Position|PipelineInput|Aliases                       |
|-----------|--------|--------|-------------|------------------------------|
|`[Boolean]`|false   |named   |False        |AllowRespondIncomingPxeRequest|



#### **CertificateExpirationTimeUtc**

Specify a date and time when the self-signed certificate expires.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|false   |named   |False        |



#### **CertificatePassword**

Specify a secure string password for a PKI client certificate specified in CertificatePath .






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **CertificatePath**

Specify the path for a PKI client certificate to import for HTTPS communication. Use the CertificatePassword parameter for the certificate's password.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ClearMacAddressForRespondingPxeRequest**

Add this parameter to remove the array of MAC addresses that the distribution point uses to respond to PXE requests.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ClientCommunicationType**

Specifies how clients or devices communicate with the distribution point. If you specify `Https`, use the CertificatePath and CertificatePassword parameters to specify the PKI certificate to use.



Valid Values:

* Http
* Https






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[ComputerCommunicationType]`|false   |named   |False        |



#### **ClientConnectionType**

Specifies the client connection type.



Valid Values:

* Intranet
* Internet
* InternetAndIntranet






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[ClientConnectionTypes]`|false   |named   |False        |



#### **ClientTransferRate**

Specify the client transfer rate.



Valid Values:

* None
* ProfileCustom
* Profile10Mbps
* Profile100Mbps
* Profile1Gbps






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[NetworkProfile]`|false   |named   |False        |



#### **ContentMonitoringPriority**

Specify the content monitoring priority.



Valid Values:

* Lowest
* Low
* Medium
* High
* Highest






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[Priority]`|false   |named   |False        |



#### **ContentValidationSchedule**

If you use the EnableContentValidation parameter, use this parameter to specify the schedule when the distribution point validates content. To create a schedule token object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                |
|-----------------|--------|--------|-------------|-----------------------|
|`[IResultObject]`|false   |named   |False        |ValidateContentSchedule|



#### **Description**

Specify an optional description for the distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DiskSpaceDoinc**

When you use the EnableDoinc parameter, use this parameter to specify the amount of disk space to be used for Microsoft Connected Cache. Use the DiskSpaceUnit parameter to determine if this value is disk space in GB or a percentage value.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **DiskSpaceUnit**

Use this parameter with DiskSpaceDoinc to determine if that value is disk space in GB or a percentage value.



Valid Values:

* GB
* Percentage






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[DiskSpaceEnum]`|false   |named   |False        |



#### **EnableAnonymous**

Indicates that the distribution point permits anonymous connections from Configuration Manager clients to the content library.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableBranchCache**

Indicates that clients that use Windows BranchCache are allowed to download content from this on-premises distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableContentValidation**

Indicates that content validation is enabled for this distribution point. Use the ContentValidationSchedule parameter to specify the schedule.






|Type       |Required|Position|PipelineInput|Aliases              |
|-----------|--------|--------|-------------|---------------------|
|`[Boolean]`|false   |named   |False        |EnableValidateContent|



#### **EnableDoinc**

Set this parameter to `$true` to enable this distribution point to be used as a Microsoft Connected Cache server. For more information, see Microsoft Connected Cache in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/microsoft-connected-cache).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableLedbat**

Enable distribution points to use network congestion control with Windows LEDBAT. This feature can adjust the download speed to use the unused network bandwidth.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableMaintenanceMode**

Set this parameter to `$true` to enable maintenance mode (/mem/configmgr/core/servers/deploy/configure/install-and-configure-distribution-points#bkmk_maint).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableMulticast**

Enable multicast for the distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableNonWdsPxe**

Enable the Configuration Manager PXE responder on the distribution point. When you enable a PXE responder without Windows Deployment Service (WDS), Configuration Manager installs its PXE responder service on the distribution point.


For more information, see enable PXE on the distribution point (/mem/configmgr/core/servers/deploy/configure/install-and-configure-distribution-points#bkmk_config-pxe).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnablePullDP**

When set to `$True`, the distribution point can pull content from other distribution points. Use this parameter with the SourceDPRank and SourceDistributionPoint parameters.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnablePxe**

Enable PXE on the distribution point. When you enable PXE, Configuration Manager installs Windows Deployment Services (WDS) on the server, if it's not already installed. WDS is the service that supports PXE boot to install Windows images over the network.






|Type       |Required|Position|PipelineInput|Aliases         |
|-----------|--------|--------|-------------|----------------|
|`[Boolean]`|false   |named   |False        |EnablePxeSupport|



#### **EnableScheduledMulticast**

Indicates whether you can schedule when Configuration Manager deploys the OS image from the distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUnknownComputerSupport**

Enable support for unknown computers. Unknown computers are devices that Configuration Manager hasn't yet discovered.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EndIPAddress**

Specifies the ending IP address in a range of multicast addresses that Configuration Manager uses to send data to clients.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **EndUdpPort**

Specifies the ending UDP port in a range of multicast UDP ports that Configuration Manager uses to send data to clients.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **Force**

Use this parameter to add a duplicate certificate without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a distribution point object to configure. To get this object, use the Get-CMDistributionPoint (Get-CMDistributionPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases          |
|-----------------|--------|--------|--------------|-----------------|
|`[IResultObject]`|true    |0       |True (ByValue)|DistributionPoint|



#### **KeepWds**

Indicates whether the distribution point keeps Windows Deployment Services (WDS) or removes it if you disable PXE.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **LocalDriveDoinc**

When you use the EnableDoinc parameter, use this parameter to select the drive to be used for the Microsoft Connected Cache. If you specify `Automatic`, Configuration Manager selects the drive with the most free space.



Valid Values:

* Automatic
* A:
* B:
* C:
* D:
* E:
* F:
* G:
* H:
* I:
* J:
* K:
* L:
* M:
* N:
* O:
* P:
* Q:
* R:
* S:
* T:
* U:
* V:
* W:
* X:
* Y:
* Z:






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **MacAddressForRespondingPxeRequest**

Specify an array of MAC addresses that the distribution point uses to respond to PXE requests.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **MinimumSessionSize**

Specifies how many client requests must be received before a scheduled multicast starts to deploy an OS.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MulticastMaximumClientCount**

Specifies the maximum number of clients that can download the OS from this distribution point.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **PxePassword**

Specify the PXE password as a secure string.






|Type            |Required|Position|PipelineInput|Aliases                |
|----------------|--------|--------|-------------|-----------------------|
|`[SecureString]`|false   |named   |False        |ComputersUsePxePassword|



#### **PxeServerResponseDelaySec**

Specifies how long the distribution point delays before it responds to computer requests when you use multiple PXE-enabled distribution points. By default, the Configuration Manager PXE service point responds first to network PXE requests. This integer value is in seconds.






|Type     |Required|Position|PipelineInput|Aliases                      |
|---------|--------|--------|-------------|-----------------------------|
|`[Int32]`|false   |named   |False        |PxeServerResponseDelaySeconds|



#### **ReassignSiteCode**

Use this parameter to reassign the distribution point to a new site. Specify the three-letter site code as a string value.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **RemoveBoundaryGroupName**

Removes an array of boundary groups by name from the distribution point.






|Type        |Required|Position|PipelineInput|Aliases                 |
|------------|--------|--------|-------------|------------------------|
|`[String[]]`|false   |named   |False        |RemoveBoundaryGroupNames|



#### **RemoveMacAddressForRespondingPxeRequest**

Removes an array of MAC addresses that the distribution point uses to respond to PXE requests.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **RespondToAllNetwork**

Indicates that the distribution point responds to PXE requests that arrive on any of its network interfaces.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RetainDoincCache**

When you use the EnableDoinc parameter, use this parameter to keep the content on the server when you disable the Microsoft Connected Cache.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **SessionStartDelayMins**

Specifies the number of minutes that Configuration Manager waits before it responds to the first multicast deployment request.






|Type     |Required|Position|PipelineInput|Aliases                 |
|---------|--------|--------|-------------|------------------------|
|`[Int32]`|false   |named   |False        |SessionStartDelayMinutes|



#### **SiteCode**

Specify the three-character code for the Configuration Manager site that hosts this site system role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specify the FQDN of the server that hosts this site system role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **SourceDistributionPoint**

When you use the EnablePullDP parameter, use this parameter to specify an array of distribution point sources. This distribution point pulls content from the specified sources. Use the SourceDPRank parameter to prioritize these sources.






|Type        |Required|Position|PipelineInput|Aliases                 |
|------------|--------|--------|-------------|------------------------|
|`[String[]]`|false   |named   |False        |SourceDistributionPoints|



#### **SourceDPRank**

Specify an array that contains the priorities for the distribution point sources from which this distribution point can pull content. When source distribution points have the same priority, the pull distribution point randomly selects a source. Use this parameter with the EnablePullDP and SourceDistributionPoint parameters.






|Type       |Required|Position|PipelineInput|Aliases      |
|-----------|--------|--------|-------------|-------------|
|`[Int32[]]`|false   |named   |False        |SourceDPRanks|



#### **StartIPAddress**

Specifies the starting IP address in a range of multicast addresses that Configuration Manager uses to send data to clients.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StartUdpPort**

Specifies the starting UDP port in a range of multicast UDP ports that Configuration Manager uses to send data to clients.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UseAnyRangeIP**

Indicates that multicast uses IP addresses within any range.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UseComputerAccount**

Indicates that the distribution point uses its computer account as the multicast connection account when it connects to the primary site database.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **UserDeviceAffinity**

Specifies how you want the distribution point to associate users with their devices for PXE deployments.



Valid Values:

* DoNotUse
* AllowWithManualApproval
* AllowWithAutomaticApproval






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[UserDeviceAffinityType]`|false   |named   |False        |



#### **UserName**

Specify the name of the user that the distribution point uses to connect to the primary site database. Use the format `domain\username`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Set-CMDistributionPoint [-InputObject] <IResultObject> [-AddBoundaryGroupName <String[]>] [-AddMacAddressForRespondingPxeRequest <String[]>] [-AgreeDoincLicense <Boolean>] [-AllowFallbackForContent <Boolean>] [-AllowPreStaging <Boolean>] [-AllowProxyTraffic <Boolean>] [-AllowPxeResponse <Boolean>] [-CertificateExpirationTimeUtc <DateTime>] [-CertificatePassword <SecureString>] [-CertificatePath <String>] [-ClearMacAddressForRespondingPxeRequest] [-ClientCommunicationType {Http | Https}] [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ClientTransferRate {None | ProfileCustom | Profile10Mbps | Profile100Mbps | Profile1Gbps}] [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] [-ContentValidationSchedule <IResultObject>] [-Description <String>] [-DisableWildcardHandling] [-DiskSpaceDoinc <Int32>] [-DiskSpaceUnit {GB | Percentage}] [-EnableAnonymous <Boolean>] [-EnableBranchCache <Boolean>] [-EnableContentValidation <Boolean>] [-EnableDoinc <Boolean>] [-EnableLedbat <Boolean>] [-EnableMaintenanceMode <Boolean>] [-EnableMulticast <Boolean>] [-EnableNonWdsPxe <Boolean>] [-EnablePullDP <Boolean>] [-EnablePxe <Boolean>] [-EnableScheduledMulticast <Boolean>] [-EnableUnknownComputerSupport <Boolean>] [-EndIPAddress <String>] [-EndUdpPort <Int32>] [-Force] [-ForceWildcardHandling] [-KeepWds <Boolean>] [-LocalDriveDoinc {Automatic | A: | B: | C: | D: | E: | F: | G: | H: | I: | J: | K: | L: | M: | N: | O: | P: | Q: | R: | S: | T: | U: | V: | W: | X: | Y: | Z:}] [-MacAddressForRespondingPxeRequest <String[]>] [-MinimumSessionSize <Int32>] [-MulticastMaximumClientCount <Int32>] [-PassThru] [-PxePassword <SecureString>] [-PxeServerResponseDelaySec <Int32>] [-ReassignSiteCode <String>] [-RemoveBoundaryGroupName <String[]>] [-RemoveMacAddressForRespondingPxeRequest <String[]>] [-RespondToAllNetwork] [-RetainDoincCache <Boolean>] [-SessionStartDelayMins <Int32>] [-SourceDistributionPoint <String[]>] [-SourceDPRank <Int32[]>] [-StartIPAddress <String>] [-StartUdpPort <Int32>] [-UseAnyRangeIP] [-UseComputerAccount] [-UserDeviceAffinity {DoNotUse | AllowWithManualApproval | AllowWithAutomaticApproval}] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMDistributionPoint [-SiteSystemServerName] <String> [-AddBoundaryGroupName <String[]>] [-AddMacAddressForRespondingPxeRequest <String[]>] [-AgreeDoincLicense <Boolean>] [-AllowFallbackForContent <Boolean>] [-AllowPreStaging <Boolean>] [-AllowProxyTraffic <Boolean>] [-AllowPxeResponse <Boolean>] [-CertificateExpirationTimeUtc <DateTime>] [-CertificatePassword <SecureString>] [-CertificatePath <String>] [-ClearMacAddressForRespondingPxeRequest] [-ClientCommunicationType {Http | Https}] [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ClientTransferRate {None | ProfileCustom | Profile10Mbps | Profile100Mbps | Profile1Gbps}] [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] [-ContentValidationSchedule <IResultObject>] [-Description <String>] [-DisableWildcardHandling] [-DiskSpaceDoinc <Int32>] [-DiskSpaceUnit {GB | Percentage}] [-EnableAnonymous <Boolean>] [-EnableBranchCache <Boolean>] [-EnableContentValidation <Boolean>] [-EnableDoinc <Boolean>] [-EnableLedbat <Boolean>] [-EnableMaintenanceMode <Boolean>] [-EnableMulticast <Boolean>] [-EnableNonWdsPxe <Boolean>] [-EnablePullDP <Boolean>] [-EnablePxe <Boolean>] [-EnableScheduledMulticast <Boolean>] [-EnableUnknownComputerSupport <Boolean>] [-EndIPAddress <String>] [-EndUdpPort <Int32>] [-Force] [-ForceWildcardHandling] [-KeepWds <Boolean>] [-LocalDriveDoinc {Automatic | A: | B: | C: | D: | E: | F: | G: | H: | I: | J: | K: | L: | M: | N: | O: | P: | Q: | R: | S: | T: | U: | V: | W: | X: | Y: | Z:}] [-MacAddressForRespondingPxeRequest <String[]>] [-MinimumSessionSize <Int32>] [-MulticastMaximumClientCount <Int32>] [-PassThru] [-PxePassword <SecureString>] [-PxeServerResponseDelaySec <Int32>] [-ReassignSiteCode <String>] [-RemoveBoundaryGroupName <String[]>] [-RemoveMacAddressForRespondingPxeRequest <String[]>] [-RespondToAllNetwork] [-RetainDoincCache <Boolean>] [-SessionStartDelayMins <Int32>] [-SiteCode <String>] [-SourceDistributionPoint <String[]>] [-SourceDPRank <Int32[]>] [-StartIPAddress <String>] [-StartUdpPort <Int32>] [-UseAnyRangeIP] [-UseComputerAccount] [-UserDeviceAffinity {DoNotUse | AllowWithManualApproval | AllowWithAutomaticApproval}] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
