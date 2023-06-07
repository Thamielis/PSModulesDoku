Add-CMDistributionPoint
-----------------------




### Synopsis
Add a distribution point role.



---


### Description

The Add-CMDistributionPoint cmdlet creates a distribution point on a site system server. A distribution point is a site system role that Configuration Manager uses to store files for clients to download, such as application content, software packages, software updates, operating system images, and boot images.



Before you can make content available to client computers, assign a site system server as a distribution point. You can add the distribution point site role to a new site system server or add the site role to an existing site system server.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDistributionPoint](Get-CMDistributionPoint)



* [Get-CMSiteSystemServer](Get-CMSiteSystemServer)



* [New-CMSchedule](New-CMSchedule)



* [Set-CMDistributionPoint](Set-CMDistributionPoint)



* [Update-CMDistributionPoint](Update-CMDistributionPoint)



* [Remove-CMDistributionPoint](Remove-CMDistributionPoint)



* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)



* [Install and configure distribution points in Configuration Manager](Install and configure distribution points in Configuration Manager)





---


### Examples
#### Example 1: Add a site by using a site system server object
```PowerShell
$Date = [DateTime]::Now.AddYears(30)
$SystemServer = Get-CMSiteSystemServer -SiteSystemServerName "MySiteSys_11310.Contoso.com"
Add-CMDistributionPoint -InputObject $SystemServer -CertificateExpirationTimeUtc $Date
```

#### Example 2: Add a site by using the pipeline
```PowerShell
$Date = [DateTime]::Now.AddYears(30)
Get-CMSiteSystemServer -SiteSystemServerName "MySiteSys_11310.Contoso.com" | Add-CMDistributionPoint -CertificateExpirationTimeUtc $Date
```



---


### Parameters
#### **AllowFallbackForContent**

Indicates that clients outside of the boundary groups associated with a site system can fall back and use this site system as a source location for content when no other site systems are available.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **AllowPreStaging**

Indicates that the distribution point can pre-stage contents.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **AllowProxyTraffic**

Enables the site system to use a proxy server when it connects to the internet.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[Switch]`|false   |named   |False        |EnableCloudGateway|



#### **AllowPxeResponse**

Indicates that the distribution point can respond to PXE requests.






|Type      |Required|Position|PipelineInput|Aliases                       |
|----------|--------|--------|-------------|------------------------------|
|`[Switch]`|false   |named   |False        |AllowRespondIncomingPxeRequest|



#### **CertificateExpirationTimeUtc**

Specifies, in UTC format, the date and time when the certificate expires.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|true    |named   |False        |



#### **CertificatePassword**

Specifies, as a secure string, the password for a PKI client certificate.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|true    |named   |False        |



#### **CertificatePath**

Specifies the import path for a PKI client certificate.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ClientConnectionType**

Specifies the client connection type.



Valid Values:

* Intranet
* Internet
* InternetAndIntranet






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[ClientConnectionTypes]`|false   |named   |False        |



#### **ContentMonitoringPriority**

Specifies the content monitoring priority.



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

Specifies a schedule token object that the distribution point uses to validate content on a scheduled basis. To create a schedule token object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                |
|-----------------|--------|--------|-------------|-----------------------|
|`[IResultObject]`|false   |named   |False        |ValidateContentSchedule|



#### **Description**

Specifies a description for the distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAnonymous**

Indicates that the distribution point permits anonymous connections from Configuration Manager clients to the content library.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableBranchCache**

Indicates that clients that use Windows BranchCache are allowed to download content from an on-premises distribution point. Content downloads from cloud-based distribution points can always be shared by clients that use Windows BranchCache.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableContentValidation**

Indicates that content validation is enabled for this distribution point.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[Switch]`|false   |named   |False        |EnableValidateContent|



#### **EnableLedbat**

Enable distribution points to use network congestion control with Windows LEDBAT. This feature can adjust the download speed to use the unused network bandwidth.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableMulticast**

Indicates that multicast is enabled for this distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableNonWdsPxe**

Indicates whether the Configuration Manager PXE responder is enabled on the distribution point. When you enable a PXE responder without Windows Deployment Service (WDS), Configuration Manager installs its PXE responder service on the distribution point.


For more information, see enable PXE on the distribution point (/mem/configmgr/core/servers/deploy/configure/install-and-configure-distribution-points#bkmk_config-pxe).






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnablePullDP**

When set to `$True`, the distribution point is able to pull content from other distribution points.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnablePxe**

Indicates that PXE is enabled on the distribution point.


When you enable PXE, Configuration Manager installs Windows Deployment Services on the server, if required. Windows Deployment Service is the service that performs the PXE boot to install operating systems. After you create the distribution point, Configuration Manager installs a provider in Windows Deployment Services that uses the PXE boot functions.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[Switch]`|false   |named   |False        |EnablePxeSupport|



#### **EnableScheduledMulticast**

Indicates whether you can schedule when Configuration Manager deploys the operating system image from the distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableSsl**

Indicates that SSL is enabled on this distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableUnknownComputerSupport**

Indicates that support for unknown computers is enabled. Unknown computers are computers that are not managed by Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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

Specify a site system server object to add the distribution point role. To get this object, use the Get-CMSiteSystemServer (Get-CMSiteSystemServer.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|SiteServer|



#### **InstallInternetServer**

Indicates that Configuration Manager installs and configures Internet Information Services (IIS) on the server if it isn't already installed. The distribution point role requires IIS.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **MacAddressForRespondingPxeRequest**

Specifies an array of MAC addresses that the distribution point uses to respond to PXE requests.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **MinimumFreeSpaceMB**

Specifies the amount of free space to reserve on each drive used by this distribution point. When this limit is reached, Configuration Manager chooses a different drive and continues the copy process to that drive. Content files can span multiple drives.


Starting in version 2107, the default minimum free space changed from 50 MB to 500 MB .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MinimumSessionSize**

Specifies how many client requests must be received before a scheduled multicast starts to deploy the operating system.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **MulticastMaximumClientCount**

Specifies the maximum number of clients that can download the operating system from this distribution point.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PrimaryContentLibraryLocation**

Specifies the primary content location. Configuration Manager copies content to the primary content location until the amount of free space reaches the value that you specified for the MinimumFreeSpaceMB parameter.



Valid Values:

* Automatic
* A
* B
* C
* D
* E
* F
* G
* H
* I
* J
* K
* L
* M
* N
* O
* P
* Q
* R
* S
* T
* U
* V
* W
* X
* Y
* Z






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[DriveType]`|false   |named   |False        |



#### **PrimaryPackageShareLocation**

Specifies the primary package share location. Configuration Manager copies content to the primary package share location until the amount of free space reaches the value that you specified for the MinimumFreeSpaceMB parameter.



Valid Values:

* Automatic
* A
* B
* C
* D
* E
* F
* G
* H
* I
* J
* K
* L
* M
* N
* O
* P
* Q
* R
* S
* T
* U
* V
* W
* X
* Y
* Z






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[DriveType]`|false   |named   |False        |



#### **PxePassword**

Specifies, as a secure string, the PXE password.






|Type            |Required|Position|PipelineInput|Aliases                |
|----------------|--------|--------|-------------|-----------------------|
|`[SecureString]`|false   |named   |False        |ComputersUsePxePassword|



#### **PxeServerResponseDelaySec**

Specifies, in seconds, how long the distribution point delays before it responds to computer requests when you are using multiple PXE-enabled distribution points. By default, the Configuration Manager PXE service point responds first to network PXE requests.






|Type     |Required|Position|PipelineInput|Aliases                      |
|---------|--------|--------|-------------|-----------------------------|
|`[Int32]`|false   |named   |False        |PxeServerResponseDelaySeconds|



#### **SecondaryContentLibraryLocation**

Specifies the secondary content location.



Valid Values:

* Automatic
* A
* B
* C
* D
* E
* F
* G
* H
* I
* J
* K
* L
* M
* N
* O
* P
* Q
* R
* S
* T
* U
* V
* W
* X
* Y
* Z






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[DriveType]`|false   |named   |False        |



#### **SecondaryPackageShareLocation**

Specifies the secondary package share location.



Valid Values:

* Automatic
* A
* B
* C
* D
* E
* F
* G
* H
* I
* J
* K
* L
* M
* N
* O
* P
* Q
* R
* S
* T
* U
* V
* W
* X
* Y
* Z






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[DriveType]`|false   |named   |False        |



#### **SessionStartDelayMins**

Specifies the number of minutes that Configuration Manager waits before it responds to the first deployment request.






|Type     |Required|Position|PipelineInput|Aliases                 |
|---------|--------|--------|-------------|------------------------|
|`[Int32]`|false   |named   |False        |SessionStartDelayMinutes|



#### **SiteCode**

Specify the three-character code for the site that hosts this site system role.


Starting in version 2111, you can't specify the central administration site (CAS) for this parameter, which doesn't support any client-facing site system roles.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of a server to host a site system role.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |0       |False        |Name<br/>ServerName|



#### **SourceDistributionPoint**

Specifies an array of distribution point sources from which this distribution point can pull content.






|Type        |Required|Position|PipelineInput|Aliases                 |
|------------|--------|--------|-------------|------------------------|
|`[String[]]`|false   |named   |False        |SourceDistributionPoints|



#### **SourceDPRank**

Specifies an array containing the priorities for the distribution point sources from which this distribution point can pull content. Source distribution points with the same priority are randomly selected.






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

Specifies the name of the user that the distribution point uses to connect to the primary site database. Use the format domain\username.






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
For more information on this return object and its properties, see SMS_SCI_SysResUse server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_sci_sysresuse-server-wmi-class).



---


### Syntax
```PowerShell
Add-CMDistributionPoint [-AllowFallbackForContent] [-AllowPreStaging] [-AllowProxyTraffic] [-AllowPxeResponse] -CertificateExpirationTimeUtc <DateTime> [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] [-ContentValidationSchedule <IResultObject>] [-Description <String>] [-DisableWildcardHandling] [-EnableAnonymous] [-EnableBranchCache] [-EnableContentValidation] [-EnableLedbat] [-EnableMulticast] [-EnableNonWdsPxe] [-EnablePullDP] [-EnablePxe] [-EnableScheduledMulticast <Boolean>] [-EnableSsl] [-EnableUnknownComputerSupport] [-EndIPAddress <String>] [-EndUdpPort <Int32>] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallInternetServer] [-MacAddressForRespondingPxeRequest <String[]>] [-MinimumFreeSpaceMB <Int32>] [-MinimumSessionSize <Int32>] [-MulticastMaximumClientCount <Int32>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PxePassword <SecureString>] [-PxeServerResponseDelaySec <Int32>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SessionStartDelayMins <Int32>] [-SourceDistributionPoint <String[]>] [-SourceDPRank <Int32[]>] [-StartIPAddress <String>] [-StartUdpPort <Int32>] [-UserDeviceAffinity {DoNotUse | AllowWithManualApproval | AllowWithAutomaticApproval}] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPoint [-SiteSystemServerName] <String> [-AllowFallbackForContent] [-AllowPreStaging] [-AllowProxyTraffic] [-AllowPxeResponse] -CertificateExpirationTimeUtc <DateTime> [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] [-ContentValidationSchedule <IResultObject>] [-Description <String>] [-DisableWildcardHandling] [-EnableAnonymous] [-EnableBranchCache] [-EnableContentValidation] [-EnableLedbat] [-EnableMulticast] [-EnableNonWdsPxe] [-EnablePullDP] [-EnablePxe] [-EnableScheduledMulticast <Boolean>] [-EnableSsl] [-EnableUnknownComputerSupport] [-EndIPAddress <String>] [-EndUdpPort <Int32>] [-Force] [-ForceWildcardHandling] [-InstallInternetServer] [-MacAddressForRespondingPxeRequest <String[]>] [-MinimumFreeSpaceMB <Int32>] [-MinimumSessionSize <Int32>] [-MulticastMaximumClientCount <Int32>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PxePassword <SecureString>] [-PxeServerResponseDelaySec <Int32>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SessionStartDelayMins <Int32>] [-SiteCode <String>] [-SourceDistributionPoint <String[]>] [-SourceDPRank <Int32[]>] [-StartIPAddress <String>] [-StartUdpPort <Int32>] [-UserDeviceAffinity {DoNotUse | AllowWithManualApproval | AllowWithAutomaticApproval}] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPoint [-SiteSystemServerName] <String> [-AllowFallbackForContent] [-AllowPreStaging] [-AllowProxyTraffic] [-AllowPxeResponse] -CertificatePassword <SecureString> -CertificatePath <String> [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] [-ContentValidationSchedule <IResultObject>] [-Description <String>] [-DisableWildcardHandling] [-EnableAnonymous] [-EnableBranchCache] [-EnableContentValidation] [-EnableLedbat] [-EnableMulticast] [-EnableNonWdsPxe] [-EnablePullDP] [-EnablePxe] [-EnableScheduledMulticast <Boolean>] [-EnableSsl] [-EnableUnknownComputerSupport] [-EndIPAddress <String>] [-EndUdpPort <Int32>] [-Force] [-ForceWildcardHandling] [-InstallInternetServer] [-MacAddressForRespondingPxeRequest <String[]>] [-MinimumFreeSpaceMB <Int32>] [-MinimumSessionSize <Int32>] [-MulticastMaximumClientCount <Int32>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PxePassword <SecureString>] [-PxeServerResponseDelaySec <Int32>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SessionStartDelayMins <Int32>] [-SiteCode <String>] [-SourceDistributionPoint <String[]>] [-SourceDPRank <Int32[]>] [-StartIPAddress <String>] [-StartUdpPort <Int32>] [-UserDeviceAffinity {DoNotUse | AllowWithManualApproval | AllowWithAutomaticApproval}] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDistributionPoint [-AllowFallbackForContent] [-AllowPreStaging] [-AllowProxyTraffic] [-AllowPxeResponse] -CertificatePassword <SecureString> -CertificatePath <String> [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] [-ContentValidationSchedule <IResultObject>] [-Description <String>] [-DisableWildcardHandling] [-EnableAnonymous] [-EnableBranchCache] [-EnableContentValidation] [-EnableLedbat] [-EnableMulticast] [-EnableNonWdsPxe] [-EnablePullDP] [-EnablePxe] [-EnableScheduledMulticast <Boolean>] [-EnableSsl] [-EnableUnknownComputerSupport] [-EndIPAddress <String>] [-EndUdpPort <Int32>] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-InstallInternetServer] [-MacAddressForRespondingPxeRequest <String[]>] [-MinimumFreeSpaceMB <Int32>] [-MinimumSessionSize <Int32>] [-MulticastMaximumClientCount <Int32>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PxePassword <SecureString>] [-PxeServerResponseDelaySec <Int32>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SessionStartDelayMins <Int32>] [-SourceDistributionPoint <String[]>] [-SourceDPRank <Int32[]>] [-StartIPAddress <String>] [-StartUdpPort <Int32>] [-UserDeviceAffinity {DoNotUse | AllowWithManualApproval | AllowWithAutomaticApproval}] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
