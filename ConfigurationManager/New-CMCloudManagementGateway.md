New-CMCloudManagementGateway
----------------------------




### Synopsis
Create a cloud management gateway.



---


### Description

Use this cmdlet to create a cloud management gateway (CMG) service in Azure. For more information on how to use this cmdlet to create a cloud management gateway (CMG), see 2010 release notes: Cloud management gateway (/powershell/sccm/2010-release-notes#cloud-management-gateway).



For more information, see CMG Overview (/mem/configmgr/core/clients/manage/cmg/overview).



Starting in version 2010, the following parameters were removed from this cmdlet:



- GovernmentSubscription



- ManagementCertificatePassword



- ManagementCertificatePath



- PassThru



- RootCertificatePath



- ServiceCertificatePassword



- ServiceCertificatePath



- ServiceCName






For more information on the other changes to this cmdlet in version 2010, see 2010 release notes (/powershell/sccm/2010-release-notes#cloud-management-gateway).


> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).




---


### Related Links
* [Get-CMCloudManagementGateway](Get-CMCloudManagementGateway)



* [Remove-CMCloudManagementGateway](Remove-CMCloudManagementGateway)



* [Set-CMCloudManagementGateway](Set-CMCloudManagementGateway)



* [Start-CMCloudManagementGateway](Start-CMCloudManagementGateway)



* [Stop-CMCloudManagementGateway](Stop-CMCloudManagementGateway)



* [Import-CMAADServerApplication](Import-CMAADServerApplication)



* [Import-CMAADClientApplication](Import-CMAADClientApplication)



* [New-CMCloudManagementAzureService](New-CMCloudManagementAzureService)



* [New-CMCloudManagementGateway](New-CMCloudManagementGateway)



* [Add-CMCloudManagementGatewayConnectionPoint](Add-CMCloudManagementGatewayConnectionPoint)



* [Set-CMCloudManagementAzureService](Set-CMCloudManagementAzureService)



* [CMG Overview](CMG Overview)





---


### Examples
#### Example 1
```PowerShell
$Path = "c:\TestPath\RootCA.cer"
$Type = [Microsoft.ConfigurationManagement.AdminConsole.AzureServices.CertificateStore]::RootCA
$Cert =@{$Path = $Type}

$Password = '0HNy*c@63kAe' | ConvertTo-SecureString -AsPlainText -Force

New-CMCloudManagementGateway -ServiceCertPath "c:\TestPath\ServiceCert.pfx" -EnvironmentSetting AzurePublicCloud -SubscriptionId "e517b8cb-a969-4d1e-b2ea-ae1e6c052020" -ServiceCertPassword $Password -ServiceName "GraniteFalls.CloudApp.Net" -Description "EastUS CMG for Contoso" -Region EastUS -VMInstanceCount 2 -CARootCert $Cert -CheckClientCertRevocation $False -EnforceProtocol $True -IsUsingExistingGroup $true -GroupName "Resource group 1"
```

#### Example 2
```PowerShell
New-CMCloudManagementGateway -ServiceCertPath "c:\TestPath\ServiceCert.pfx" -EnvironmentSetting AzurePublicCloud -SubscriptionId "e517b8cb-a969-4d1e-b2ea-ae1e6c052020" -ServiceCertPassword $Password -ServiceName "GraniteFalls.CloudApp.Net" -Description "EastUS CMG for Contoso" -Region EastUS -VMInstanceCount 2 -CARootCert $Cert -CheckClientCertRevocation $False -EnforceProtocol $True -GroupName "Resource group 1" -EnableCloudDPFunction $true -EnableTrafficOut $true -TrafficOutStopService $true -TrafficOutGB 10000 -TrafficWarningPct 50 -TrafficCriticalPct 90 -EnableStorageQuota $true -StorageQuotaGB 2000 -StorageWarningPct 50 -StorageCriticalPct 90 -Force
```



---


### Parameters
#### **CARootCert**

Applies to version 2010 and later. Add root certificates to the cloud service.






|Type         |Required|Position|PipelineInput|Aliases                                     |
|-------------|--------|--------|-------------|--------------------------------------------|
|`[Hashtable]`|false   |named   |False        |CARootCertification<br/>CARootCertifications|



#### **CheckClientCertRevocation**

Set this parameter to `true` to verify client certificate revocation. A certificate revocation list (CRL) must be publicly published for this verification to work. For more information, see Publish the certificate revocation list (/mem/configmgr/core/clients/manage/cmg/security-and-privacy-for-cloud-management-gateway#bkmk_crl).






|Type       |Required|Position|PipelineInput|Aliases                          |
|-----------|--------|--------|-------------|---------------------------------|
|`[Boolean]`|false   |named   |False        |VerifyClientCertificateRevocation|



#### **Description**

An optional description of the CMG, to better identify it in the Configuration Manager console.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableCloudDPFunction**

Applies to version 2010 and later. Enable or disable the option to Allow CMG to function as a cloud distribution point and serve content from Azure storage .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableStorageQuota**

Applies to version 2010 and later. Enable or disable the option to Specify storage alert threshold .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableTrafficOut**

Applies to version 2010 and later. Enable or disable the option to Turn on 14-day threshold and alerts for monitoring outbound data transfer .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnforceProtocol**

Applies to version 2010 and later. Enable or disable the option to Enforce TLS 1.2 .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnvironmentSetting**

Specify Azure environment to deploy the CMG: in the global Azure cloud (`AzurePublicCloud`) or the Azure Government cloud (`AzureUSGovernmentCloud`).



Valid Values:

* AzurePublicCloud
* AzureUSGovernmentCloud
* AzureChinaCloud
* AzureGermanCloud






|Type                |Required|Position|PipelineInput|Aliases               |
|--------------------|--------|--------|-------------|----------------------|
|`[AzureEnvironment]`|false   |named   |False        |AzureEnvironmentOption|



#### **Force**

Applies to version 2010 and later. Run the command without asking for confirmation. If the service certificate contains multiple DNS names, use this parameter to avoid warnings from the cmdlet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GroupName**

Applies to version 2010 and later. Specify the name of the Azure resource group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **IsUsingExistingGroup**

Applies to version 2010 and later. Specify if the Azure resource group already exists.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Region**

Specify the Azure service region, for example: `WestUS2`.



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
|`[AzureRegion]`|false   |named   |False        |



#### **ServerAppClientId**

Applies to version 2010 and later. Specify the client ID of the Azure AD server app. Use this parameter for non-user interaction mode. In the CMG properties, this value is the Azure AD app name .






|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|true    |named   |False        |ServerApplicationClientId|



#### **ServiceCertPassword**

Applies to version 2010 and later. Specify the password for the service certificate.






|Type            |Required|Position|PipelineInput|Aliases                   |
|----------------|--------|--------|-------------|--------------------------|
|`[SecureString]`|true    |named   |False        |ServiceCertificatePassword|



#### **ServiceCertPath**

Applies to version 2010 and later. Specify the path to the service certificate. For more information, see CMG server authentication certificate (/mem/configmgr/core/clients/manage/cmg/server-auth-cert).






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|true    |named   |False        |ServiceCertificatePath|



#### **ServiceName**

Applies to version 2010 and later. Specify the Azure service name. If you don't specify this parameter, Configuration Manager uses the service certificate's first DNS name. If the certificate has more than one DNS name, use this parameter to specify which one to use.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StorageCriticalPct**

Applies to version 2010 and later. Specify an integer value for the Generate Critical alert (% of storage alert threshold) . For example, `90`.






|Type     |Required|Position|PipelineInput|Aliases               |
|---------|--------|--------|-------------|----------------------|
|`[Int32]`|false   |named   |False        |StorageCriticalPercent|



#### **StorageQuotaGB**

Applies to version 2010 and later. Specify an integer value for the Storage alert threshold (GB) . For example, `2`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **StorageWarningPct**

Applies to version 2010 and later. Specify an integer value for the Generate Warning alert (% of storage alert threshold) . For example, `50`.






|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|false   |named   |False        |StorageWarningPercent|



#### **SubscriptionId**

Specify the ID of the Azure subscription where you want to deploy this new cloud service. The format of this value is a standard GUID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TrafficCriticalPct**

If you enable alerts for monitoring outbound data transfer, specify the percentage of threshold for raising a Critical alert. This value is `90` by default.






|Type     |Required|Position|PipelineInput|Aliases               |
|---------|--------|--------|-------------|----------------------|
|`[Int32]`|false   |named   |False        |TrafficCriticalPercent|



#### **TrafficOutGB**

If you enable storage alerts, use this parameter to specify the storage alert threshold in GB . The default value is `2`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TrafficOutStopService**

Applies to version 2010 and later. Enable or disable the option to Stop this service when the critical threshold is exceeded .






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **TrafficWarningPct**

If you enable alerts for monitoring outbound data transfer, specify the percentage of threshold for raising a Warning alert. This value is `50` by default.






|Type     |Required|Position|PipelineInput|Aliases              |
|---------|--------|--------|-------------|---------------------|
|`[Int32]`|false   |named   |False        |TrafficWarningPercent|



#### **VMInstanceCount**

Specify the instance count of virtual machines for the CMG in Azure.






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






---


### Notes




---


### Syntax
```PowerShell
New-CMCloudManagementGateway [-CARootCert <Hashtable>] [-CheckClientCertRevocation <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-EnableCloudDPFunction <Boolean>] [-EnableStorageQuota <Boolean>] [-EnableTrafficOut <Boolean>] [-EnforceProtocol <Boolean>] [-EnvironmentSetting {AzurePublicCloud | AzureUSGovernmentCloud}] [-Force] [-ForceWildcardHandling] [-GroupName <String>] [-IsUsingExistingGroup <Boolean>] [-Region {EastUS | SouthCentralUS | WestEurope | SoutheastAsia | WestUS2 | WestCentralUS}] -ServiceCertPassword <SecureString> -ServiceCertPath <String> [-ServiceName <String>] [-StorageCriticalPct <Int32>] [-StorageQuotaGB <Int32>] [-StorageWarningPct <Int32>] [-SubscriptionId <String>] [-TrafficCriticalPct <Int32>] [-TrafficOutGB <Int32>] [-TrafficOutStopService <Boolean>] [-TrafficWarningPct <Int32>] [-VMInstanceCount <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMCloudManagementGateway [-CARootCert <Hashtable>] [-CheckClientCertRevocation <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-EnableCloudDPFunction <Boolean>] [-EnableStorageQuota <Boolean>] [-EnableTrafficOut <Boolean>] [-EnforceProtocol <Boolean>] [-EnvironmentSetting {AzurePublicCloud | AzureUSGovernmentCloud}] [-Force] [-ForceWildcardHandling] -GroupName <String> [-Region {EastUS | SouthCentralUS | WestEurope | SoutheastAsia | WestUS2 | WestCentralUS}] -ServerAppClientId <String> -ServiceCertPassword <SecureString> -ServiceCertPath <String> [-ServiceName <String>] [-StorageCriticalPct <Int32>] [-StorageQuotaGB <Int32>] [-StorageWarningPct <Int32>] -SubscriptionId <String> [-TrafficCriticalPct <Int32>] [-TrafficOutGB <Int32>] [-TrafficOutStopService <Boolean>] [-TrafficWarningPct <Int32>] [-VMInstanceCount <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
