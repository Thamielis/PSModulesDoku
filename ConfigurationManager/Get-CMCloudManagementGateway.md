Get-CMCloudManagementGateway
----------------------------




### Synopsis
Get a cloud management gateway (CMG).



---


### Description

Use this cmdlet to get an object for a cloud management gateway (CMG) that's configured for the site.



For more information, see CMG Overview (/mem/configmgr/core/clients/manage/cmg/overview).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMCloudManagementGateway](New-CMCloudManagementGateway)



* [Remove-CMCloudManagementGateway](Remove-CMCloudManagementGateway)



* [Set-CMCloudManagementGateway](Set-CMCloudManagementGateway)



* [Start-CMCloudManagementGateway](Start-CMCloudManagementGateway)



* [Stop-CMCloudManagementGateway](Stop-CMCloudManagementGateway)



* [Sync-CMCloudManagementGateway](Sync-CMCloudManagementGateway)



* [CMG Overview](CMG Overview)





---


### Examples
#### Example 1
```PowerShell
Get-CMCloudManagementGateway -Name "GraniteFalls.cloudapp.net"
```



---


### Parameters
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



#### **Id**

Specify the site's ID for the Azure service. The Id is the integer value stored in the site database for the service. For example, run the following SQL query, and look at the ID column: `select * from Azure_CloudService`.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |AzureServiceId|



#### **Name**

Specify the service name for the CMG in Azure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





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
Get-CMCloudManagementGateway [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMCloudManagementGateway [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
