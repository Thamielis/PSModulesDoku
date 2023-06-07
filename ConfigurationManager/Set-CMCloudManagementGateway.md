Set-CMCloudManagementGateway
----------------------------




### Synopsis
Configure a cloud management gateway (CMG).



---


### Description

Use this cmdlet to configure a cloud management gateway (CMG).



For more information, see CMG Overview (/mem/configmgr/core/clients/manage/cmg/overview).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCloudManagementGateway](Get-CMCloudManagementGateway)



* [New-CMCloudManagementGateway](New-CMCloudManagementGateway)



* [Remove-CMCloudManagementGateway](Remove-CMCloudManagementGateway)



* [Start-CMCloudManagementGateway](Start-CMCloudManagementGateway)



* [Stop-CMCloudManagementGateway](Stop-CMCloudManagementGateway)



* [CMG Overview](CMG Overview)





---


### Examples
#### Example 1: Change the CMG alerts configuration
```PowerShell
Set-CMCloudManagementGateway -Name "GraniteFalls" -EnableTrafficOut $true -TrafficOutGB 10000 -TrafficWarningPct 50 -TrafficCriticalPct 90 -EnableStorageQuota $true -StorageQuotaGB 2000 -StorageWarningPct 50 -StorageCriticalPct 90
```

#### Example 2: Change the number of virtual machines for the CMG service
```PowerShell
Set-CMCloudManagementGateway -Name "GraniteFalls" -VMInstancesCount 4
```

#### Example 3: Enable the CMG to serve content from Azure storage
```PowerShell
Set-CMCloudManagementGateway -Name "GraniteFalls" -EnableCloudDPFunction $true
```

#### Example 4: Add two new certificate authorities
```PowerShell
$path1 = "folder\root.cer"
$type1 = [Microsoft.ConfigurationManagement.AdminConsole.AzureServices.CertificateStore]::RootCA

$path2 = "folder\intermediate.cer"
$type2 = [Microsoft.ConfigurationManagement.AdminConsole.AzureServices.CertificateStore]::IntermediateCA

$cert = @{$path1 = $type1; $path2 = $type2}

Set-CMCloudManagementGateway -Name "GraniteFalls" -CARootCert $cert
```

#### Example 5: Update the CMG server authentication certificate
```PowerShell
Set-CMCloudManagementGateway -Name "GraniteFalls" -ServiceCertPath "c:\TestPath\NewServiceCert.pfx" -ServiceCertPassword (ConvertTo-SecureString -String "tX*xJ11Nuo^B" -AsPlainText -Force)
```

#### Example 6: Remove a root certificate from a CMG
```PowerShell
Set-CMCloudManagementGateway -Name "GraniteFalls" -RemoveCertThumbprints "A7CBA0014DEF847593569D05003D5B96A1D6A627"
```



---


### Parameters
#### **CARootCert**

Add root certificates to the cloud service.






|Type         |Required|Position|PipelineInput|Aliases                                 |
|-------------|--------|--------|-------------|----------------------------------------|
|`[Hashtable]`|false   |named   |False        |CARootCertificate<br/>CARootCertificates|



#### **CheckClientCertRevocation**

Set this parameter to `true` to verify client certificate revocation. A certificate revocation list (CRL) must be publicly published for this verification to work. For more information, see Publish the certificate revocation list (/mem/configmgr/core/clients/manage/cmg/security-and-privacy-for-cloud-management-gateway#bkmk_crl).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **Description**

Specify an optional description of this CMG service to better identify it.






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



#### **Force**

Run the command without asking for confirmation. If the service certificate contains multiple DNS names, use this parameter to avoid warnings from the cmdlet.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the site's ID for the Azure service. The Id is the integer value stored in the site database for the service. For example, run the following SQL query, and look at the ID column: `select * from Azure_CloudService`.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |AzureServiceId|



#### **InputObject**

Specify a CMG object to configure. To get this object, use the Get-CMCloudManagementGateway (Get-CMCloudManagementGateway.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of the CMG to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveCertThumbprints**

Applies to version 2010 and later. Specify one or more certificate thumbprints to remove them as root or intermediate certificate authorities from the CMG.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[String[]]`|false   |named   |False        |



#### **ServiceCertPassword**

Applies to version 2006 and later. Specify the password for the certificate in the -ServiceCertPath .






|Type            |Required|Position|PipelineInput|Aliases                   |
|----------------|--------|--------|-------------|--------------------------|
|`[SecureString]`|false   |named   |False        |ServiceCertificatePassword|



#### **ServiceCertPath**

Applies to version 2006 and later. Specify the path to the service certificate. For more information, see CMG server authentication certificate (/mem/configmgr/core/clients/manage/cmg/server-auth-cert).






|Type      |Required|Position|PipelineInput|Aliases               |
|----------|--------|--------|-------------|----------------------|
|`[String]`|false   |named   |False        |ServiceCertificatePath|



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



#### **TrafficCriticalPct**

If you enable alerts for monitoring outbound data transfer, specify the percentage of threshold for raising a Critical alert. This value is `90` by default.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TrafficOutGB**

If you enable storage alerts, use this parameter to specify the storage alert threshold in GB . The default value is `2`.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **TrafficOutStopService**

Applies to version 2010 and later. Enable or disable the option to Stop this service when the critical threshold is exceeded .






|Type       |Required|Position|PipelineInput|Aliases              |
|-----------|--------|--------|-------------|---------------------|
|`[Boolean]`|false   |named   |False        |StopTrafficOutService|



#### **TrafficWarningPct**

If you enable alerts for monitoring outbound data transfer, specify the percentage of threshold for raising a Warning alert. This value is `50` by default.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **VMInstanceCount**

Applies to version 2010 and later. Specify the instance count of virtual machines.






|Type     |Required|Position|PipelineInput|Aliases         |
|---------|--------|--------|-------------|----------------|
|`[Int32]`|false   |named   |False        |VMInstancesCount|



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
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Set-CMCloudManagementGateway [-CARootCert <Hashtable>] [-CheckClientCertRevocation <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-EnableCloudDPFunction <Boolean>] [-EnableStorageQuota <Boolean>] [-EnableTrafficOut <Boolean>] [-EnforceProtocol <Boolean>] [-Force] [-ForceWildcardHandling] -Id <String> [-PassThru] [-RemoveCertThumbprints <String[]>] [-ServiceCertPassword <SecureString>] [-ServiceCertPath <String>] [-StorageCriticalPct <Int32>] [-StorageQuotaGB <Int32>] [-StorageWarningPct <Int32>] [-TrafficCriticalPct <Int32>] [-TrafficOutGB <Int32>] [-TrafficOutStopService <Boolean>] [-TrafficWarningPct <Int32>] [-VMInstanceCount <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCloudManagementGateway [-CARootCert <Hashtable>] [-CheckClientCertRevocation <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-EnableCloudDPFunction <Boolean>] [-EnableStorageQuota <Boolean>] [-EnableTrafficOut <Boolean>] [-EnforceProtocol <Boolean>] [-Force] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-RemoveCertThumbprints <String[]>] [-ServiceCertPassword <SecureString>] [-ServiceCertPath <String>] [-StorageCriticalPct <Int32>] [-StorageQuotaGB <Int32>] [-StorageWarningPct <Int32>] [-TrafficCriticalPct <Int32>] [-TrafficOutGB <Int32>] [-TrafficOutStopService <Boolean>] [-TrafficWarningPct <Int32>] [-VMInstanceCount <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCloudManagementGateway [-CARootCert <Hashtable>] [-CheckClientCertRevocation <Boolean>] [-Description <String>] [-DisableWildcardHandling] [-EnableCloudDPFunction <Boolean>] [-EnableStorageQuota <Boolean>] [-EnableTrafficOut <Boolean>] [-EnforceProtocol <Boolean>] [-Force] [-ForceWildcardHandling] -Name <String> [-PassThru] [-RemoveCertThumbprints <String[]>] [-ServiceCertPassword <SecureString>] [-ServiceCertPath <String>] [-StorageCriticalPct <Int32>] [-StorageQuotaGB <Int32>] [-StorageWarningPct <Int32>] [-TrafficCriticalPct <Int32>] [-TrafficOutGB <Int32>] [-TrafficOutStopService <Boolean>] [-TrafficWarningPct <Int32>] [-VMInstanceCount <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
