Get-CMSoftwareUpdateContentInfo
-------------------------------




### Synopsis
Get software update content information.



---


### Description

Starting in version 2107, use this cmdlet to get software update content information. For example,



- File name



- File size



- SHA-1 hash



- Source URL






> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).




---


### Related Links
* [Get-CMSoftwareUpdate](Get-CMSoftwareUpdate)





---


### Examples
#### Example 1: Get software update content information for a specific update
```PowerShell
$update = Get-CMSoftwareUpdate -ArticleId "5004237" -Fast
Get-CMSoftwareUpdateContentInfo -InputObject $update[1]
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

Specify the CI_ID of the software update to get its content information. This value is an integer, for example `1584792`.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |CIId<br/>CI_ID|



#### **InputObject**

Specify a software update object to get its content information. To get this object, use the Get-CMSoftwareUpdate (Get-CMSoftwareUpdate.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the localized display name of a software update to get its content information. It matches the exact string, it doesn't accept wildcard characters.






|Type      |Required|Position|PipelineInput|Aliases             |
|----------|--------|--------|-------------|--------------------|
|`[String]`|true    |named   |False        |LocalizedDisplayName|



#### **UniqueId**

Specify the Unique Update ID of the software update to get its content information. This value is a GUID, and also the CI_UniqueID property on the software update object.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |CI_UniqueID|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_CIContentFiles


* IResultObject#SMS_CIContentFiles






---


### Notes
For more information on this return object and its properties, see SMS_CIContentFiles server WMI class (/mem/configmgr/develop/reference/sum/sms_cicontentfiles-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMSoftwareUpdateContentInfo [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdateContentInfo [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdateContentInfo [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [<CommonParameters>]
```
```PowerShell
Get-CMSoftwareUpdateContentInfo [-DisableWildcardHandling] [-ForceWildcardHandling] -UniqueId <String> [<CommonParameters>]
```
