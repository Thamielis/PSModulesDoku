Get-CMSiteUpdateInstallStatus
-----------------------------




### Synopsis
Gets a site update install status.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>
```



---


### Parameters
#### **Complete**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**








|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |PackageName|



#### **Step**





Valid Values:

* Simple
* Download
* Prerequisite
* Installation
* Replication
* PostInstallation
* InstallationAll
* All






|Type                 |Required|Position|PipelineInput|
|---------------------|--------|--------|-------------|
|`[InstallStatusStep]`|false   |named   |False        |





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
Get-CMSiteUpdateInstallStatus [-Complete] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Step {All | Download | Installation | Prerequisite | Simple | InstallationAll | PostInstallation | Replication}] [<CommonParameters>]
```
```PowerShell
Get-CMSiteUpdateInstallStatus [-Complete] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Step {All | Download | Installation | Prerequisite | Simple | InstallationAll | PostInstallation | Replication}] [<CommonParameters>]
```
