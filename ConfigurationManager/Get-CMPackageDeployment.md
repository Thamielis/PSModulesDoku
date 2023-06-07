Get-CMPackageDeployment
-----------------------




### Synopsis
Gets a package deployment from Configuration Manager.



---


### Description

The Get-CMPackageDeployment cmdlet starts deployment of a specified software package to computers that belong to a Configuration Manager collection.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMPackageDeployment](New-CMPackageDeployment)



* [Get-CMPackageDeploymentStatus](Get-CMPackageDeploymentStatus)



* [Set-CMPackageDeployment](Set-CMPackageDeployment)



* [Remove-CMPackageDeployment](Remove-CMPackageDeployment)



* [Get-CMPackage](Get-CMPackage)





---


### Examples
#### Example 1
```PowerShell
PS XYZ:\> Get-CMPackageDeployment -PackageId $thisPackage.packageid
```
This command gets a package deployment by the package id.


---


### Parameters
#### **Collection**

Specifies the user collection.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **CollectionId**

Specifies the ID of a device or user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **CollectionName**

Specifies the name of a user collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeploymentId**

Specifies the ID of a deployment.






|Type      |Required|Position|PipelineInput|Aliases                                |
|----------|--------|--------|-------------|---------------------------------------|
|`[String]`|false   |named   |False        |AdvertisementID<br/>PackageDeploymentID|



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

Specifies a package.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|false   |named   |True (ByValue)|Package|



#### **Name**

Specifies the name of a package.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |PackageName|



#### **PackageId**

Specifies the ID of a package.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|false   |named   |False        |SmsObjectId|



#### **ProgramName**

Specifies the name of a program.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Summary**

Add this parameter to return the SMS_DeploymentSummary WMI class (/mem/configmgr/develop/reference/apps/sms_deploymentsummary-server-wmi-class)object.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_DeploymentSummary


* IResultObject#SMS_DeploymentSummary


* IResultObject[]#SMS_Advertisement


* IResultObject#SMS_Advertisement






---


### Notes
For more information on these return objects and their properties, see the following articles:

- SMS_DeploymentSummary server WMI class (/mem/configmgr/develop/reference/apps/sms_deploymentsummary-server-wmi-class)- SMS_Advertisement server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_advertisement-server-wmi-class)



---


### Syntax
```PowerShell
Get-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DeploymentId <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-ProgramName <String>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-InputObject <IResultObject>] [-ProgramName <String>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-ProgramName <String>] [-Summary] [<CommonParameters>]
```
```PowerShell
Get-CMPackageDeployment [-Collection <IResultObject>] [-CollectionId <String>] [-CollectionName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-PackageId <String>] [-ProgramName <String>] [-Summary] [<CommonParameters>]
```
