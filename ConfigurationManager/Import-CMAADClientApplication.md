Import-CMAADClientApplication
-----------------------------




### Synopsis
Create the Azure Active Directory (Azure AD) client app definition in Configuration Manager.



---


### Description

Use this cmdlet to import the client app from Azure AD, and define it for the Configuration Manager site. It assumes that an Azure administrator already created the app in Azure AD. In Azure AD, this app is known as a native app registration.



For more information on how to use this cmdlet to create a cloud management gateway (CMG), see 2010 release notes: Cloud management gateway (/powershell/sccm/2010-release-notes#cloud-management-gateway).



For more information about Azure AD apps in Configuration Manager, see Configure Azure services (/mem/configmgr/core/servers/deploy/configure/azure-services-wizard).



> [!NOTE] > This cmdlet might work with other Azure services, but it's only tested with the Cloud management connection to support the cloud management gateway (CMG).



---


### Related Links
* [Get-CMAADApplication](Get-CMAADApplication)



* [Import-CMAADServerApplication](Import-CMAADServerApplication)



* [Configure Azure services](Configure Azure services)





---


### Examples
#### Example 1: Import the client app based on the tenant ID
```PowerShell
Import-CMAADClientApplication -TenantId "05a349fa-298a-4427-8771-9efcdb73431e" -AppName "CmgClientApp" -ClientId "cf114f48-88db-4829-ac45-0c186e86dbf6"
```

#### Example 2: Import the client app based on the server app
```PowerShell
$serverApp = Get-CMAADApplication -TenantName "Contoso" -AppType ServerApplication -AppName "CmgServerApp"

Import-CMAADClientApplication -ServerApp $serverApp -AppName "CmgClientApp" -ClientId "cf114f48-88db-4829-ac45-0c186e86dbf6"
```



---


### Parameters
#### **AppName**

Specify the name of the app in Azure AD.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|true    |named   |False        |ApplicationName|



#### **ClientId**

Specify the Application (client) ID value of the app registration in Azure AD. The format is a standard GUID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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



#### **ServerApp**

Specify an object for the server app. To get the server app, use the Get-CMAADApplication (Get-CMAADApplication.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases          |
|-----------------|--------|--------|-------------|-----------------|
|`[IResultObject]`|true    |named   |False        |ServerApplication|



#### **TenantId**

Specify the GUID of your Azure AD tenant.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Import-CMAADClientApplication -AppName <String> -ClientId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -ServerApp <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Import-CMAADClientApplication -AppName <String> -ClientId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] -TenantId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
