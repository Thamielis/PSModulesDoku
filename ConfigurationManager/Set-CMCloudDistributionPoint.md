Set-CMCloudDistributionPoint
----------------------------




### Synopsis
Changes settings for a cloud-based distribution point.



---


### Description

The Set-CMCloudDistributionPoint cmdlet changes settings for a cloud-based distribution point.



In Configuration Manager, you can use a cloud service in Windows Azure to host a distribution point for storing files to download to clients. You can send packages and apps to and host packages and apps in cloud distribution points. For more information about cloud distribution points, see Planning for Content Management in Configuration Manager (/mem/configmgr/core/plan-design/hierarchy/fundamental-concepts-for-content-management).



You can use the Set-CMCloudDistributionPoint cmdlet to specify storage alert thresholds and warning levels for content that you deploy to a cloud distribution point. You can also use the cmdlet to configure settings that enable users and devices to access the content. You can provide a name and description for the cloud distribution point.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCloudDistributionPoint](Get-CMCloudDistributionPoint)



* [New-CMCloudDistributionPoint](New-CMCloudDistributionPoint)



* [Remove-CMCloudDistributionPoint](Remove-CMCloudDistributionPoint)



* [Start-CMCloudDistributionPoint](Start-CMCloudDistributionPoint)



* [Stop-CMCloudDistributionPoint](Stop-CMCloudDistributionPoint)





---


### Examples
#### Example 1: Set values for a distribution point
```PowerShell
PS XYZ:\> Set-CMCloudDistributionPoint -Id 16777237 -Description "Western distribution point" -Name "West01" -StorageQuotaInGB 50 -TrafficOutInGB 50
```
This command sets the description and name for a distribution point to the provided strings. It also sets values for the storage quota and data transfer.


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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of identifiers for one or more cloud distribution points. You can use a comma-separated list.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |AzureServiceId|



#### **InputObject**

Specifies a cloud distribution point object. To obtain a cloud distribution point object, you can use the Get-CMCloudDistributionPoint (Get-CMCloudDistributionPoint.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies a name for a cloud distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Specifies a new name for the cloud-based distribution point.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **StorageQuotaGB**

Specifies the threshold value, in gigabytes, that triggers errors or warnings for total content storage.






|Type     |Required|Position|PipelineInput|Aliases         |
|---------|--------|--------|-------------|----------------|
|`[Int32]`|false   |named   |False        |StorageQuotaInGB|



#### **StorageQuotaGrow**

Specifies whether the storage quota can grow. By default, the amount of stored data cannot exceed the value of the StorageQuotaInGB parameter. The default value for this parameter is $False.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **TrafficOutGB**

Specifies the threshold value, in gigabytes, that triggers errors or warnings, for monthly traffic out of Windows Azure Storage Service.






|Type     |Required|Position|PipelineInput|Aliases       |
|---------|--------|--------|-------------|--------------|
|`[Int32]`|false   |named   |False        |TrafficOutInGB|



#### **TrafficOutStopService**

Specifies whether Configuration Manager stops data transfers after the distribution point reaches the quota specified in the TrafficOutInGB parameter. The default value for this parameter is $False.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



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
Set-CMCloudDistributionPoint [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-StorageQuotaGB <Int32>] [-StorageQuotaGrow <Boolean>] [-TrafficOutGB <Int32>] [-TrafficOutStopService <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCloudDistributionPoint [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-StorageQuotaGB <Int32>] [-StorageQuotaGrow <Boolean>] [-TrafficOutGB <Int32>] [-TrafficOutStopService <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCloudDistributionPoint [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-StorageQuotaGB <Int32>] [-StorageQuotaGrow <Boolean>] [-TrafficOutGB <Int32>] [-TrafficOutStopService <Boolean>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
