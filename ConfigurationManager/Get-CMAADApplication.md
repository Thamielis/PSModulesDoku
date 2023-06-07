Get-CMAADApplication
--------------------




### Synopsis
Get the Azure Active Directory (Azure AD) app object from the site.



---


### Description

Use this cmdlet to get the Azure AD app object from the site. It's commonly used with the New-CMCloudManagementAzureService (New-CMCloudManagementAzureService.md)cmdlet.



For more information about Azure AD apps in Configuration Manager, see Configure Azure services (/mem/configmgr/core/servers/deploy/configure/azure-services-wizard).



> [!NOTE] > While some of the new cmdlets might work with other Azure services, they're only tested with the Cloud management connection to support the cloud management gateway (CMG).



---


### Related Links
* [New-CMCloudManagementAzureService](New-CMCloudManagementAzureService)



* [Get-CMAzureService](Get-CMAzureService)



* [Configure Azure services](Configure Azure services)





---


### Examples
#### Example 1: Get Azure AD client apps by tenant name
```PowerShell
Get-CMAADApplication -TenantName "Contoso" -AppType ClientApplication
```

#### Example 2: Get Azure AD server apps by tenant ID
```PowerShell
Get-CMAADApplication -TenantId "05a349fa-298a-4427-8771-9efcdb73431e" -AppType ServerApplication
```

#### Example 3: Get an Azure AD app by its name
```PowerShell
Get-CMAADApplication -AppName "CmgServerApp"
```



---


### Parameters
#### **AppName**

Specify the name of the app in Azure AD.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |named   |False        |ApplicationName|



#### **AppType**

Specify whether to target the server or client app.


In Azure AD, the server app is known as a web app registration, and the client app is known as a native app registration.



Valid Values:

* ServerApplication
* ClientApplication






|Type                    |Required|Position|PipelineInput|Aliases        |
|------------------------|--------|--------|-------------|---------------|
|`[CloudApplicationType]`|false   |named   |False        |ApplicationType|



#### **ClientId**

Specify the Application (client) ID value of the app registration in Azure AD. The format is a standard GUID.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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



#### **TenantId**

Specify the GUID of your Azure AD tenant.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **TenantName**

Specify the name of your Azure AD tenant.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





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
Get-CMAADApplication [-AppName <String>] [-AppType {ServerApplication | ClientApplication}] [-ClientId <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-TenantId <String>] [-TenantName <String>] [<CommonParameters>]
```
