Get-CMCloudDistributionPoint
----------------------------




### Synopsis
Gets cloud-based distribution points.



---


### Description

The Get-CMCloudDistributionPoint cmdlet gets one or more cloud-based distribution points in Configuration Manager.



In Configuration Manager, you can use a cloud service in Azure to host a distribution point for storing files to download to clients. You can send packages and apps to and host packages and apps in cloud distribution points. For more information about cloud distribution points, see Planning for Content Management in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management).



You can use the Get-CMCloudDistributionPoint cmdlet to get distribution points to use with other cmdlets. For example, you might want to get a distribution point and then use the Stop-CMCloudDistributionPoint (Stop-CMCloudDistributionPoint.md)cmdlet to suspend it.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMCloudDistributionPoint](New-CMCloudDistributionPoint)



* [Remove-CMCloudDistributionPoint](Remove-CMCloudDistributionPoint)



* [Set-CMCloudDistributionPoint](Set-CMCloudDistributionPoint)



* [Start-CMCloudDistributionPoint](Start-CMCloudDistributionPoint)



* [Stop-CMCloudDistributionPoint](Stop-CMCloudDistributionPoint)





---


### Examples
#### Example 1: Get all cloud distribution points
```PowerShell
PS XYZ:\> Get-CMCloudDistributionPoint
```
This command gets all the cloud distribution points.
#### Example 2: Get a cloud distribution point by name
```PowerShell
PS XYZ:\> Get-CMCloudDistributionPoint -Name "West01"
```
This command gets a distribution point named West01.
#### Example 3: Get a cloud distribution point by ID
```PowerShell
PS XYZ:\> Get-CMCloudDistributionPoint -Id "16777230"
```
This command gets a distribution point with the specified ID.


---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointGroup**

Specifies a CMDistributionPointGroup object. To get a CMDistributionPointGroup object, use the Get-CMDistributionPointGroup (Get-CMDistributionPointGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DistributionPointGroupId**

Specifies the ID of a distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DistributionPointGroupName**

Specifies the name of a distribution point group.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of identifiers for cloud distribution points. You can use a comma separated list.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |AzureServiceId|



#### **Name**

Specifies the name of a cloud distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_AzureService


* IResultObject#SMS_AzureService


* IResultObject[]#SMS_SCI_SysResUse


* IResultObject#SMS_SCI_SysResUse






---


### Notes




---


### Syntax
```PowerShell
Get-CMCloudDistributionPoint [-DisableWildcardHandling] -DistributionPointGroup <IResultObject> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCloudDistributionPoint [-DisableWildcardHandling] -DistributionPointGroupId <String> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCloudDistributionPoint [-DisableWildcardHandling] -DistributionPointGroupName <String> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCloudDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMCloudDistributionPoint [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
