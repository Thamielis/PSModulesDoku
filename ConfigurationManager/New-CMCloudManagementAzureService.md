New-CMCloudManagementAzureService
---------------------------------




### Synopsis
Create the Azure service for Cloud Management in Configuration Manager.



---


### Description

Use this cmdlet to create the Azure service in Configuration Manager for Cloud Management .



For more information on how to use this cmdlet to create a cloud management gateway (CMG), see 2010 release notes: Cloud management gateway (/powershell/sccm/2010-release-notes#cloud-management-gateway).



For more information about the Cloud Management service, see CMG Overview (/mem/configmgr/core/clients/manage/cmg/overview).



---


### Related Links
* [Get-CMAADApplication](Get-CMAADApplication)



* [Import-CMAADServerApplication](Import-CMAADServerApplication)



* [Import-CMAADClientApplication](Import-CMAADClientApplication)



* [New-CMCloudManagementGateway](New-CMCloudManagementGateway)



* [Add-CMCloudManagementGatewayConnectionPoint](Add-CMCloudManagementGatewayConnectionPoint)



* [Set-CMCloudManagementAzureService](Set-CMCloudManagementAzureService)



* [CMG Overview](CMG Overview)





---


### Examples
#### Example 1
```PowerShell
$serverApp = Get-CMAADApplication -TenantName "Contoso" -AppType ServerApplication -AppName "CmgServerApp"

$clientApp = Get-CMAADApplication -TenantName "Contoso" -AppType ClientApplication -AppName "CmgClientApp"

New-CMCloudManagementAzureService -Name "Contoso" -Description "Azure Service" -ServerApp $serverApp -ClientApp $clientApp -AzureEnvironmentOption AzurePublicCloud
```



---


### Parameters
#### **AddGroupName**

Specify an Azure Active Directory (Azure AD) group name to discover. Use this parameter with the EnableGroupDiscovery parameter.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |AddGroupNames|



#### **AzureEnvironmentOption**

Specify whether this service is in the global Azure cloud (`AzurePublicCloud`), or the Azure Government cloud (`AzureUSGovernmentCloud`).



Valid Values:

* AzurePublicCloud
* AzureUSGovernmentCloud
* AzureChinaCloud
* AzureGermanCloud






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[AzureEnvironment]`|false   |named   |False        |



#### **ClientApp**

Specify an object for the client app registration. To get this app, use the Get-CMAADApplication (Get-CMAADApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                                      |
|-----------------|--------|--------|-------------|---------------------------------------------|
|`[IResultObject]`|true    |named   |False        |ClientApplication<br/>NativeClientApplication|



#### **Description**

Specify an optional description for the service.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableGroupDeltaDiscovery**

Set this parameter to `true` to enable delta discovery for Azure AD group discovery. Use this parameter with the EnableGroupDiscovery parameter. Use the GroupDeltaDiscoveryMins parameter to configure the delta discovery interval.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableGroupDiscovery**

Set this parameter to `true` to enable Azure AD group discovery. When you enable this discovery method, also configure the following parameters:


* AddGroupName : Add Azure AD groups to discover - EnableGroupDeltaDiscovery : Configure delta discovery - GroupDeltaDiscoveryMins : Delta discovery interval - GroupDiscoverySchedule : Full polling schedule


For more information on this discovery method, see Azure Active Directory user group discovery (/mem/configmgr/core/servers/deploy/configure/about-discovery-methods#bkmk_azuregroupdisco).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUserDeltaDiscovery**

Set this parameter to `true` to enable delta discovery for Azure AD user discovery. Use this parameter with the EnableUserDiscovery parameter.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **EnableUserDiscovery**

Set this parameter to `true` to enable Azure AD user discovery. When you enable this discovery method, also configure the following parameters:


* EnableUserDeltaDiscovery : Configure delta discovery - UserDeltaDiscoveryMins : Delta discovery interval - UserDiscoverySchedule : Full polling schedule


For more information on this discovery method, see Azure Active Directory user discovery (/mem/configmgr/core/servers/deploy/configure/about-discovery-methods#azureaddisc).






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **GroupDeltaDiscoveryMins**

When you enable delta discovery for Azure AD group discovery with the EnableGroupDeltaDiscovery parameter, use this parameter to configure the delta discovery interval. The integer value you specify is the polling interval in minutes.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **GroupDiscoverySchedule**

Specify a schedule object for the Azure AD group discovery full polling schedule. To get this object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **Name**

Specify a name to distinguish the Cloud Management service in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ServerApp**

Specify an object for the server app registration. To get this app, use the Get-CMAADApplication (Get-CMAADApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases                                        |
|-----------------|--------|--------|-------------|-----------------------------------------------|
|`[IResultObject]`|true    |named   |False        |WebApp<br/>WebApplication<br/>ServerApplication|



#### **UserDeltaDiscoveryMins**

When you enable delta discovery for Azure AD user discovery with the EnableUserDeltaDiscovery parameter, use this parameter to configure the delta discovery interval. The integer value you specify is the polling interval in minutes.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **UserDiscoverySchedule**

Specify a schedule object for the Azure AD user discovery full polling schedule. To get this object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






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
* IResultObject#SMS_Azure_CloudService






---


### Notes
You can't enable Azure AD group sync when you create the service. To enable group sync, use the Set-CMCloudManagementAzureService (Set-CMCloudManagementAzureService.md)cmdlet with the EnableAADGroupSync parameter.



---


### Syntax
```PowerShell
New-CMCloudManagementAzureService [-AddGroupName <String[]>] [-AzureEnvironmentOption {AzurePublicCloud | AzureUSGovernmentCloud}] -ClientApp <IResultObject> [-Description <String>] [-DisableWildcardHandling] [-EnableGroupDeltaDiscovery <Boolean>] [-EnableGroupDiscovery <Boolean>] [-EnableUserDeltaDiscovery <Boolean>] [-EnableUserDiscovery <Boolean>] [-ForceWildcardHandling] [-GroupDeltaDiscoveryMins <Int32>] [-GroupDiscoverySchedule <IResultObject>] -Name <String> -ServerApp <IResultObject> [-UserDeltaDiscoveryMins <Int32>] [-UserDiscoverySchedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
