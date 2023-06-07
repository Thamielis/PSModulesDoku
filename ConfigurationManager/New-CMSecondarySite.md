New-CMSecondarySite
-------------------




### Synopsis
Create a secondary site.



---


### Description

The New-CMSecondarySite cmdlet creates a secondary site. For more information, see Prepare to install Configuration Manager sites (/mem/configmgr/core/servers/deploy/install/prepare-to-install-sites).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMInstallationSourceFile](New-CMInstallationSourceFile)



* [New-CMSqlServerSetting](New-CMSqlServerSetting)



* [Remove-CMSecondarySite](Remove-CMSecondarySite)





---


### Examples
#### Example 1: Create a secondary site
```PowerShell
$CIObj = New-CMSqlServerSetting -CopySqlServerExpressOnSecondarySite

New-CMSecondarySite -CertificateExpirationTimeUtc "2/1/2020 12:00 AM" -CreateSelfSignedCertificate -Https -InstallationSourceFile "\\ContosoServer1\SourceFiles" -InstallInternetServer $True -ParentSiteCode "CM1" -ServerName "server2.corp.contoso.com" -SiteCode "CM2" -SiteName "Contoso remote site" -SqlServerSetting $CIObj
```



---


### Parameters
#### **AllowFallbackForContent**

Indicates whether clients can use a fallback source location for content.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **AllowPreStaging**

Indicates whether the secondary site can prestage content.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **BoundaryGroup**

Specify an array of boundary group objects for this site system. To get this object, use the Get-CMBoundaryGroup (Get-CMBoundaryGroup.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases       |
|-------------------|--------|--------|-------------|--------------|
|`[IResultObject[]]`|false   |named   |False        |BoundaryGroups|



#### **CertificateExpirationTimeUtc**

Specifies the date and time at which the self-signed certificate expires for a distribution point on the secondary site.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|true    |named   |False        |



#### **CertificatePassword**

Specifies the password for the PKI imported certificate for the distribution point.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|true    |named   |False        |



#### **CertificatePath**

Specifies the import path for the PKI issued certificate that the distribution point uses. This parameter applies when the secondary site has installed and configured IIS to create a distribution point.






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



#### **CreateSelfSignedCertificate**

Indicates that the secondary site creates a self-signed certificate for the distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAnonymous**

Indicates whether client computers communicate anonymously with the distribution point. This parameter applies when the secondary site has installed and configured IIS to create a distribution point.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableBranchCache**

Indicates that clients that use Windows BranchCache are allowed to download content from an on-premises distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWhenDuplicateCertificate**

Indicates whether Configuration Manager overwrites a duplicate certificate when you import a PKI client certificate for the secondary site.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Http**

Indicates that client computers communicate with the distribution point by using HTTP. This parameter applies when the secondary site has installed and configured IIS to create a distribution point. \






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **Https**

Indicates that client computers communicate with the distribution point by using HTTPS. This parameter applies when the secondary site has installed and configured IIS to create a distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **ImportCertificate**

Indicates that the cmdlet imports a PKI certificate instead of using a self-signed certificate for the distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **InstallationFolder**

Specifies the installation folder on the secondary site server where the cmdlet installs the site files.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |InstallDir|



#### **InstallationSourceFile**

Specifies an array of installation source file objects for Configuration Manager. To get this object, use the New-CMInstallationSourceFile (New-CMInstallationSourceFile.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|true    |named   |False        |



#### **InstallInternetServer**

Specifies whether to install and configure IIS if Configuration Manager requires it. This parameter must be `$True` before the cmdlet installs the site system role for the distribution point on the secondary site.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **MinFreeSpaceMB**

Specifies the amount of space, in megabytes, to reserve on each drive that the distribution point uses. This value determines the remaining free space on the drive after the distribution stores content on the drive.


Starting in version 2107, the default minimum free space changed from 200 MB to 500 MB .






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **PrimaryContentLibraryLocation**

Specifies a primary content library location.



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

Specifies a primary package share location.



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



#### **PrimarySiteCode**

Specify the three-character site code of the parent site.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|false   |named   |False        |ParentSiteCode|



#### **SecondaryContentLibraryLocation**

Specifies a secondary content library location.



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

Specifies a secondary package share location.



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



#### **SecondarySiteCode**

Specify a unique three-character site code for the secondary site.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |SiteCode|



#### **ServerName**

Specify the fully qualified domain name (FQDN) of the server to use as the secondary site server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteName**

Specifies the site name that helps identify the secondary site.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SqlServerSetting**

Specifies an array of SQL Server settings object in Configuration Manager. To get this object, use the New-CMSqlServerSetting (New-CMSqlServerSetting.md)cmdlet.






|Type               |Required|Position|PipelineInput|
|-------------------|--------|--------|-------------|
|`[IResultObject[]]`|true    |named   |False        |



#### **ValidateContentSchedule**

Specifies an object that represents a schedule type. It determines how frequently Configuration Manager validates the integrity of packages on the distribution point. To create a schedule token object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






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
None





---


### Outputs
* IResultObject#SMS_Site


* IResultObject#SMS_SCI_SiteDefinition


* IResultObject#SMS_SCI_SysResUse


* IResultObject[]#SMS_SCI_Address






---


### Notes
For more information on this return object and its properties, see SMS_SCI_SysResUse server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_sci_sysresuse-server-wmi-class).



---


### Syntax
```PowerShell
New-CMSecondarySite [-AllowFallbackForContent <Boolean>] [-AllowPreStaging <Boolean>] [-BoundaryGroup <IResultObject[]>] -CertificateExpirationTimeUtc <DateTime> [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] -CreateSelfSignedCertificate [-DisableWildcardHandling] [-EnableAnonymous <Boolean>] [-EnableBranchCache] [-ForceWildcardHandling] -Http [-InstallationFolder <String>] -InstallationSourceFile <IResultObject[]> [-InstallInternetServer <Boolean>] [-MinFreeSpaceMB <Int32>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimarySiteCode <String>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] -SecondarySiteCode <String> -ServerName <String> -SiteName <String> -SqlServerSetting <IResultObject[]> [-ValidateContentSchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSecondarySite [-AllowFallbackForContent <Boolean>] [-AllowPreStaging <Boolean>] [-BoundaryGroup <IResultObject[]>] -CertificateExpirationTimeUtc <DateTime> [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] -CreateSelfSignedCertificate [-DisableWildcardHandling] [-EnableBranchCache] [-ForceWildcardHandling] -Https [-InstallationFolder <String>] -InstallationSourceFile <IResultObject[]> [-InstallInternetServer <Boolean>] [-MinFreeSpaceMB <Int32>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimarySiteCode <String>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] -SecondarySiteCode <String> -ServerName <String> -SiteName <String> -SqlServerSetting <IResultObject[]> [-ValidateContentSchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSecondarySite [-AllowFallbackForContent <Boolean>] [-AllowPreStaging <Boolean>] [-BoundaryGroup <IResultObject[]>] -CertificatePassword <SecureString> -CertificatePath <String> [-ClientConnectionType {Intranet | Internet | InternetAndIntranet}] [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] [-DisableWildcardHandling] [-EnableBranchCache] [-ForceWhenDuplicateCertificate <Boolean>] [-ForceWildcardHandling] -Https -ImportCertificate [-InstallationFolder <String>] -InstallationSourceFile <IResultObject[]> [-InstallInternetServer <Boolean>] [-MinFreeSpaceMB <Int32>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimarySiteCode <String>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] -SecondarySiteCode <String> -ServerName <String> -SiteName <String> -SqlServerSetting <IResultObject[]> [-ValidateContentSchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMSecondarySite [-AllowFallbackForContent <Boolean>] [-AllowPreStaging <Boolean>] [-BoundaryGroup <IResultObject[]>] -CertificatePassword <SecureString> -CertificatePath <String> [-ContentMonitoringPriority {Lowest | Low | Medium | High | Highest}] [-DisableWildcardHandling] [-EnableAnonymous <Boolean>] [-EnableBranchCache] [-ForceWhenDuplicateCertificate <Boolean>] [-ForceWildcardHandling] -Http -ImportCertificate [-InstallationFolder <String>] -InstallationSourceFile <IResultObject[]> [-InstallInternetServer <Boolean>] [-MinFreeSpaceMB <Int32>] [-PrimaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-PrimarySiteCode <String>] [-SecondaryContentLibraryLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] [-SecondaryPackageShareLocation {Automatic | A | B | C | D | E | F | G | H | I | J | K | L | M | N | O | P | Q | R | S | T | U | V | W | X | Y | Z}] -SecondarySiteCode <String> -ServerName <String> -SiteName <String> -SqlServerSetting <IResultObject[]> [-ValidateContentSchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
