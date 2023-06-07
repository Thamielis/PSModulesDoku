New-CMCloudDistributionPoint
----------------------------




### Synopsis
Creates a cloud distribution point.



---


### Description

The New-CMCloudDistributionPoint cmdlet creates a cloud distribution point in Configuration Manager.



In Configuration Manager, you can use a cloud service in Azure to host a distribution point for storing files to download to clients. You can send packages and apps to and host packages and apps in cloud distribution points. For more information about cloud distribution points, see Planning for Content Management in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCloudDistributionPoint](Get-CMCloudDistributionPoint)



* [Remove-CMCloudDistributionPoint](Remove-CMCloudDistributionPoint)



* [Set-CMCloudDistributionPoint](Set-CMCloudDistributionPoint)



* [Start-CMCloudDistributionPoint](Start-CMCloudDistributionPoint)



* [Stop-CMCloudDistributionPoint](Stop-CMCloudDistributionPoint)





---


### Examples
#### Example 1: Create a cloud distribution point
```PowerShell
PS XYZ:\> New-CMCloudDistributionPoint -ManagementCertificatePath "C:\Certificates\Management.pfx" -Region "WestUS" -ServiceCertificatePath "C:\Certificates\Distribution.pfx" -ServiceCName "distribution-server.contoso.com" -SiteCode "ContosoSite"-SubscriptionID "81c87063-04a3-4abf-8e4c-736569bc1f60"
```
This command creates a distribution with the canonical name server.contoso.com. The distribution point is located in the WestUS Azure region and is associated with the Azure subscription 81c87063-04a3-4abf-8e4c-736569bc1f60.


---


### Parameters
#### **Description**

Specifies a description for a cloud distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnvironmentSetting**

{{ Fill EnvironmentSetting Description }}



Valid Values:

* AzurePublicCloud
* AzureUSGovernmentCloud
* AzureChinaCloud
* AzureGermanCloud






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[AzureEnvironment]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ManagementCertificatePassword**

Specifies a password for a management certificate.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **ManagementCertificatePath**

Specifies a location for a management certificate.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|true    |named   |False        |ManagementCertificate|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Region**

Specifies a region. This is the Azure region where you want to create the cloud service that hosts this distribution point. The acceptable values for this parameter are:


* AnywhereAsia


* AnywhereEurope


* AnywhereUS


* EastAsia


* EastUS


* NorthCentralUS


* NorthEurope


* SouthCentralUS


* SoutheastAsia


* WestEurope


* WestUS



Valid Values:

* AnywhereAsia
* AnywhereEurope
* AnywhereUS
* EastAsia
* EastUS
* NorthCentralUS
* NorthEurope
* SouthCentralUS
* SoutheastAsia
* WestEurope
* WestUS
* WestUS2
* WestCentralUS
* USGovernmentIowa
* USGovernmentVirginia
* USGovernmentArizona
* USGovernmentTexas
* USDoDCentral
* USDoDEast
* AustraliaEast
* AustraliaSoutheast
* BrazilSouth
* CanadaCentral
* CanadaEast
* CentralIndia
* CentralUS
* EastUS2
* JapanEast
* JapanWest
* SouthIndia
* UKSouth
* UKWest
* WestIndia
* FranceSouth
* FranceCentral
* KoreaSouth
* KoreaCentral
* AustraliaCentral
* AustraliaCentral2
* ChinaEast
* ChinaNorth
* GermanyCentral
* GermanyNortheast
* SouthAfricaNorth
* SouthAfricaWest






|Type           |Required|Position|PipelineInput|
|---------------|--------|--------|-------------|
|`[AzureRegion]`|true    |named   |False        |



#### **ServiceCertificatePassword**

Specifies a password for a service certificate.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|false   |named   |False        |



#### **ServiceCertificatePath**

Specifies a location for a service certificate.






|Type      |Required|Position|PipelineInput|Aliases           |
|----------|--------|--------|-------------|------------------|
|`[String]`|true    |named   |False        |ServiceCertificate|



#### **ServiceCName**

Specifies an alias, or CName, for a service.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SiteCode**

Specifies a Configuration Manager site code.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StorageCriticalThreshold**

Specifies the percentage for a critical alert to occur, based on the storage alert threshold.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **StorageQuotaGB**

Specifies the threshold value, in gigabytes, that triggers errors or warnings for total content storage.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **StorageWarningThreshold**

Specifies the percentage for a warning alert to occur, based on the storage alert threshold.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SubscriptionId**

Specifies a subscription ID for your Azure account. To get a subscription ID, use the Azure Management Portal.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TrafficCriticalThreshold**

Specifies the percentage for a critical alert to occur, based on the traffic out alert threshold.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TrafficOutGB**

Specifies the threshold value, in gigabytes, that triggers errors or warnings, for monthly traffic out of Azure Storage Service.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TrafficWarningThreshold**

Specifies the percentage for a warning alert to occur, based on the traffic out alert threshold.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



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
* IResultObject#SMS_AzureService


* IResultObject[]#SMS_SCI_SysResUse


* IResultObject[]#SMS_Alert


* IResultObject#SMS_Alert






---


### Notes




---


### Syntax
```PowerShell
New-CMCloudDistributionPoint [-Description <String>] [-DisableWildcardHandling] [-EnvironmentSetting {AzurePublicCloud | AzureUSGovernmentCloud}] [-ForceWildcardHandling] [-ManagementCertificatePassword <SecureString>] -ManagementCertificatePath <String> [-PassThru] -Region {AnywhereAsia | AnywhereEurope | AnywhereUS | EastAsia | EastUS | NorthCentralUS | NorthEurope | SouthCentralUS | SoutheastAsia | WestEurope | WestUS | WestUS2 | WestCentralUS | USGovernmentIowa | USGovernmentVirginia | USGovernmentArizona | USGovernmentTexas | USDoDCentral | USDoDEast | AustraliaEast | AustraliaSoutheast | BrazilSouth | CanadaCentral | CanadaEast | CentralIndia | CentralUS | EastUS2 | JapanEast | JapanWest | SouthIndia | UKSouth | UKWest | WestIndia | FranceSouth | FranceCentral | KoreaSouth | KoreaCentral | AustraliaCentral | AustraliaCentral2 | ChinaEast | ChinaNorth | GermanyCentral | GermanyNortheast | SouthAfricaNorth | SouthAfricaWest} [-ServiceCertificatePassword <SecureString>] -ServiceCertificatePath <String> -ServiceCName <String> [-SiteCode <String>] [-StorageCriticalThreshold <Int32>] [-StorageQuotaGB <Int32>] [-StorageWarningThreshold <Int32>] -SubscriptionId <String> [-TrafficCriticalThreshold <Int32>] [-TrafficOutGB <Int32>] [-TrafficWarningThreshold <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
