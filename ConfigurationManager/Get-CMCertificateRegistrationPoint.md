Get-CMCertificateRegistrationPoint
----------------------------------




### Synopsis
Gets a certificate registration point.



---


### Description

The Get-CMCertificateRegistrationPoint cmdlet gets a certificate registration point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMCertificateRegistrationPoint](Add-CMCertificateRegistrationPoint)



* [Remove-CMCertificateRegistrationPoint](Remove-CMCertificateRegistrationPoint)



* [Set-CMCertificateRegistrationPoint](Set-CMCertificateRegistrationPoint)





---


### Examples
#### Example 1: Get a certificate registration point by name
```PowerShell
PS XYZ:\> Get-CMCertificateRegistrationPoint -SiteCode SC3
```
This command gets the certificate registration point for site code SC3.
#### Example 2: Get a certificate registration point by using the pipeline
```PowerShell
PS XYZ:\> Get-CMSitesystemserver -SiteSystemServerName "SiteServer01.Contoso.com" | Get-CMCertificateRegistrationPoint
```
This command gets the site system server object named SiteServer01.Contoso.com and uses the pipeline operator to pass the object to Get-CMCertificateRegistrationPoint , which gets the certificate registration point for the site system server object.


---


### Parameters
#### **AllSite**








|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[Switch]`|false   |named   |False        |AllSites|



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

Specifies a Configuration Manager site system server object. To obtain a site system server object, use the Get-CMSiteSystemServer cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **SiteCode**

Specifies the site code of a Configuration Manager site system server.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **SiteSystemServerName**

Specifies the name of a Configuration Manager site system server.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |0       |False        |Name<br/>ServerName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Get-CMCertificateRegistrationPoint [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMCertificateRegistrationPoint [[-SiteSystemServerName] <String>] [-AllSite] [-DisableWildcardHandling] [-ForceWildcardHandling] [-SiteCode <String>] [<CommonParameters>]
```
