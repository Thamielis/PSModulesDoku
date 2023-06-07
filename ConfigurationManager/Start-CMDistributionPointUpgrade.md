Start-CMDistributionPointUpgrade
--------------------------------




### Synopsis
Upgrades a shared distribution point.



---


### Description

The Start-CMDistributionPointUpgrade cmdlet upgrades a shared distribution point to a Configuration Manager distribution point.



When you migrate from a Configuration Manager 2007 source hierarchy, you can upgrade a shared distribution point to make it a Configuration Manager distribution point. You can upgrade distribution points at both primary sites and secondary sites. The upgrade process removes the distribution point from the Configuration Manager 2007 hierarchy and makes it a site system server in the Configuration Manager hierarchy. This process also copies the existing content that is on the distributing point to a new location on the distribution point computer. The upgrade process then modifies the copy of the content to create the Configuration Manager single instance store for use with Configuration Manager content deployment. Therefore, when you upgrade a distribution point, you do not have to redistribute migrated content that was hosted on the Configuration Manager 2007 distribution point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDistributionPointGroup](Get-CMDistributionPointGroup)



* [Get-CMBoundaryGroup](Get-CMBoundaryGroup)



* [Get-CMDistributionPoint](Get-CMDistributionPoint)



* [New-CMSchedule](New-CMSchedule)





---


### Examples
#### Example 1: Upgrade a shared distribution point
```PowerShell
$CIObj = Get-CMDistributionPoint -DistributionPointGroupId "{6617708D-0F98-4898-8D05-9E882C23DCB2}"
Start-CMDistributionPointUpgrade -AllowPreStaging $True -CertificatePath "\\Contoso01\CM\Toolbox\BaseCert.txt" -SharedDistributionPoint $CIObj -SiteCode "CM1"
```



---


### Parameters
#### **AllowFallbackForContent**

Indicates whether clients can use a fallback source location for content.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowPreStaging**

Indicates whether the distribution point can pre-stage contents.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowRespondIncomingPxeRequest**

Indicates whether the distribution point can respond to pre-boot execution environment (PXE) requests.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **CertificateExpirationTimeUtc**

Specifies the date and time when the certificate expires.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|true    |named   |False        |



#### **CertificatePassword**

Specifies the password, as a secure string, for the public key infrastructure (PKI) client certificate for the distribution point.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **CertificatePath**

Specifies the import path for the PKI issued certificate that the distribution point uses.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ClientCommunicationMode**





Valid Values:

* Http
* Https






|Type                         |Required|Position|PipelineInput|
|-----------------------------|--------|--------|-------------|
|`[ComputerCommunicationType]`|false   |named   |False        |



#### **ClientConnectionType**

Specifies the client connection type. Valid values are:


* Internet


* InternetAndIntranet


* Intranet



Valid Values:

* Intranet
* Internet
* InternetAndIntranet






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[ClientConnectionTypes]`|false   |named   |False        |



#### **ContentValidationPriority**

Specifies the content validation priority. Valid values are:


* High


* Highest


* Low


* Lowest


* Medium




The default value is Lowest.




Valid Values:

* Lowest
* Low
* Medium
* High
* Highest






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[Priority]`|false   |named   |False        |



#### **DestinationSiteCode**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteCode|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAnonymous**

Indicates whether the distribution point permits anonymous connections from Configuration Manager clients to the content library.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableNonWdsPxe**

Indicates whether the Configuration Manager PXE responder is enabled on the distribution point. When you enable a PXE responder without Windows Deployment Service (WDS), Configuration Manager installs its PXE responder service on the distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnablePxeSupport**

Indicates whether to enable PXE on the distribution point.


When you enable PXE, Configuration Manager installs Windows Deployment Services on the server, if required. Windows Deployment Service is the service that performs the PXE boot to install operating systems. After you create the distribution point, Configuration Manager installs a provider in Windows Deployment Services that uses the PXE boot functions.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUnknownComputerSupport**

Indicates whether support for unknown computers is enabled. Unknown computers are computers that are not managed by Configuration Manager.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWhenDuplicateCertificate**

Indicates whether Configuration Manager overwrites a duplicate certificate when you import a PKI client certificate for the distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InitiateConnection**

Indicates whether the distribution point initiates the connection with the clients.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |Aliases                |
|-----------------|--------|--------|--------------|-----------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SharedDistributionPoint|



#### **InstallationAccount**

Specifies a Site System Installation Account. Configuration Manager 2007 Site Component Manager service uses Site System Installation Accounts to install, reinstall, uninstall, and configure site systems.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **InstallIis**








|Type       |Required|Position|PipelineInput|Aliases              |
|-----------|--------|--------|-------------|---------------------|
|`[Boolean]`|false   |named   |False        |InstallInternetServer|



#### **MacAddressForRespondingPxeRequest**

Specifies an array of media access controller (MAC) addresses that the distribution point uses to respond to pre-boot execution environment (PXE) requests.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **MinFreeSpaceMB**

Specifies the amount of free space on a drive before Configuration Manager chooses a different drive and continues the copy process to that drive. Content files can span multiple drives.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PathForSavingMigratedPackage**

Specifies the path for a copy of the migrated content.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PrimaryContentLibraryLocation**

Specifies the primary content location. Configuration Manager copies content to the primary content location until the amount of free space reaches the value that you specified for the MinFreeSpaceMB parameter. Valid values are:


* Automatic.


* Drive letter from A: through Z:.



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

Specifies the primary package share location. Configuration Manager copies content to the primary package share location until the amount of free space reaches the value that you specified for the MinFreeSpaceMB parameter. Valid values are:


* Automatic.


* Drive letter from A: through Z:.



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



#### **PublicFqdn**

Specifies the fully qualified domain name (FQDN) of the site system server that hosts the distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PxePassword**








|Type            |Required|Position|PipelineInput|Aliases                |
|----------------|--------|--------|-------------|-----------------------|
|`[SecureString]`|false   |named   |False        |ComputersUsePxePassword|



#### **PxeServerResponseDelaySec**








|Type     |Required|Position|PipelineInput|Aliases                      |
|---------|--------|--------|-------------|-----------------------------|
|`[Int32]`|false   |named   |False        |PxeServerResponseDelaySeconds|



#### **SecondaryContentLibraryLocation**

Specifies the secondary content location. Valid values are:


* Automatic.


* Drive letter from A: through Z:.



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

Specifies the secondary package share location. Valid values are:


* Automatic.


* Drive letter from A: through Z:.



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



#### **UserDeviceAffinity**

Specify how the distribution point associates users with the destination computer for PXE deployments. Valid values are:


* AllowWithAutomaticApproval


* AllowWithManualApproval


* DoNotUse



Valid Values:

* DoNotUse
* AllowWithManualApproval
* AllowWithAutomaticApproval






|Type                      |Required|Position|PipelineInput|
|--------------------------|--------|--------|-------------|
|`[UserDeviceAffinityType]`|false   |named   |False        |



#### **ValidateContentSchedule**

Specifies a CMSchedule object. A CMSchedule object defines the schedule for validating the integrity of content files on the distribution point. To create a CMSchedule object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






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
* 






---


### Notes




---


### Syntax
```PowerShell
Start-CMDistributionPointUpgrade [-AllowFallbackForContent <Boolean>] [-AllowPreStaging <Boolean>] [-AllowRespondIncomingPxeRequest <Boolean>] -CertificateExpirationTimeUtc <DateTime> [-ClientCommunicationMode {Http | Https}] [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ContentValidationPriority {Lowest | Low | Medium | High | Highest}] -DestinationSiteCode <String> [-DisableWildcardHandling] [-EnableAnonymous <Boolean>] [-EnableNonWdsPxe <Boolean>] [-EnablePxeSupport <Boolean>] [-EnableUnknownComputerSupport <Boolean>] [-ForceWildcardHandling] [-InitiateConnection <Boolean>] -InputObject <IResultObject> [-InstallationAccount <IResultObject>] [-InstallIis <Boolean>] [-MacAddressForRespondingPxeRequest <String[]>] [-MinFreeSpaceMB <Int32>] [-PathForSavingMigratedPackage <String>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PublicFqdn <String>] [-PxePassword <SecureString>] [-PxeServerResponseDelaySec <Int32>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-UserDeviceAffinity {DoNotUse | AllowWithManualApproval | AllowWithAutomaticApproval}] [-ValidateContentSchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Start-CMDistributionPointUpgrade [-AllowFallbackForContent <Boolean>] [-AllowPreStaging <Boolean>] [-AllowRespondIncomingPxeRequest <Boolean>] [-CertificatePassword <SecureString>] -CertificatePath <String> [-ClientCommunicationMode {Http | Https}] [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ContentValidationPriority {Lowest | Low | Medium | High | Highest}] -DestinationSiteCode <String> [-DisableWildcardHandling] [-EnableAnonymous <Boolean>] [-EnableNonWdsPxe <Boolean>] [-EnablePxeSupport <Boolean>] [-EnableUnknownComputerSupport <Boolean>] [-ForceWhenDuplicateCertificate <Boolean>] [-ForceWildcardHandling] [-InitiateConnection <Boolean>] -InputObject <IResultObject> [-InstallationAccount <IResultObject>] [-InstallIis <Boolean>] [-MacAddressForRespondingPxeRequest <String[]>] [-MinFreeSpaceMB <Int32>] [-PathForSavingMigratedPackage <String>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PublicFqdn <String>] [-PxePassword <SecureString>] [-PxeServerResponseDelaySec <Int32>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-UserDeviceAffinity {DoNotUse | AllowWithManualApproval | AllowWithAutomaticApproval}] [-ValidateContentSchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
