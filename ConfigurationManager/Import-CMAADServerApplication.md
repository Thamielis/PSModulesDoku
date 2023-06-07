Import-CMAADServerApplication
-----------------------------




### Synopsis
Create the Azure Active Directory (Azure AD) server app definition in Configuration Manager.



---


### Description

Use this cmdlet to import the server app from Azure AD, and define it for the Configuration Manager site. It assumes that an Azure administrator already created the app in Azure AD. In Azure AD, this app is known as a web app registration.



For more information on how to use this cmdlet to create a cloud management gateway (CMG), see 2010 release notes: Cloud management gateway (/powershell/sccm/2010-release-notes#cloud-management-gateway).



For more information about Azure AD apps in Configuration Manager, see Configure Azure services (/mem/configmgr/core/servers/deploy/configure/azure-services-wizard).



> [!NOTE] > This cmdlet might work with other Azure services, but it's only tested with the Cloud management connection to support the cloud management gateway (CMG).



---


### Related Links
* [Get-CMAADApplication](Get-CMAADApplication)



* [Import-CMAADClientApplication](Import-CMAADClientApplication)



* [Configure Azure services](Configure Azure services)





---


### Examples
#### Example 1
```PowerShell
$date = [datetime]::parseexact("11/16/2021", 'MM/dd/yyyy', $null)

Import-CMAADServerApplication -TenantName "Contoso" -TenantId "05a349fa-298a-4427-8771-9efcdb73431e" -AppName "CmgServerApp" -ClientId "7078946d-fc1c-43b7-8dee-dd6e6b00d783" -SecretKey "1uXGR^!0@Cjas6qI*J02ZeS&&zY19^hC*9" -SecretKeyExpiry $date
```



---


### Parameters
#### **AppIdUri**

Specify the Application ID URI of the app registration entry in the Azure AD portal. This value needs to be unique in your Azure AD tenant. It's in the access token used by the Configuration Manager client to request access to the service. The format is similar to https://ConfigMgrService.






|Type   |Required|Position|PipelineInput|
|-------|--------|--------|-------------|
|`[Uri]`|false   |named   |False        |



#### **AppName**

Specify the friendly name for the app. This value is the display name in the app registration.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|true    |2       |False        |ApplicationName|



#### **AzureEnvironmentOption**

Specify whether this app registration is in the global Azure cloud (`AzurePublicCloud`), or the Azure Government cloud (`AzureUSGovernmentCloud`).



Valid Values:

* AzurePublicCloud
* AzureUSGovernmentCloud
* AzureChinaCloud
* AzureGermanCloud






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[AzureEnvironment]`|false   |named   |False        |



#### **ClientId**

Specify the Application (client) ID value of the app registration in Azure AD. The format is a standard GUID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |3       |False        |



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



#### **SecretKey**

Specify the secret key for this app as copied from the Azure portal. You copied the secret key when you registered the app in Azure AD.






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[SecureString]`|true    |4       |False        |



#### **SecretKeyExpiry**

Specify the date when the SecretKey will expire. You configure this value when you create the secret key for the app in Azure AD.






|Type        |Required|Position|PipelineInput|
|------------|--------|--------|-------------|
|`[DateTime]`|true    |5       |False        |



#### **TenantId**

Specify the GUID of your Azure AD tenant.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |1       |False        |



#### **TenantName**

Specify the name of your Azure AD tenant.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |0       |False        |



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
* IResultObject#SMS_AAD_Application_Ex






---


### Notes




---


### Syntax
```PowerShell
Import-CMAADServerApplication [-TenantName] <String> [-TenantId] <String> [-AppName] <String> [-ClientId] <String> [-SecretKey] <SecureString> [-SecretKeyExpiry] <DateTime> [-AppIdUri <Uri>] [-AzureEnvironmentOption {AzurePublicCloud | AzureUSGovernmentCloud}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
