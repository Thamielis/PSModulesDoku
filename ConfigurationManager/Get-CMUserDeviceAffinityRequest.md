Get-CMUserDeviceAffinityRequest
-------------------------------




### Synopsis
Gets a request for user device affinity in Configuration Manager.



---


### Description

The Get-CMUserDeviceAffinityRequest cmdlet gets a request for user device affinity.



In Configuration Manager, user device affinity defines a relationship between a user and a device. Instead of deploying an application to a group of devices, you deploy an application to a user and Configuration Manager installs the application on all devices associated with the user.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Approve-CMUserDeviceAffinityRequest](Approve-CMUserDeviceAffinityRequest)



* [Deny-CMUserDeviceAffinityRequest](Deny-CMUserDeviceAffinityRequest)





---


### Examples
#### Example 1: Get a request for user device affinity
```PowerShell
PS XYZ:\> Get-CMUserDeviceAffinityRequest -CollectionName "All Systems"
```
This command gets a request for user device affinity for the collection named All Systems.


---


### Parameters
#### **CollectionId**

Specifies a collection ID that represents the user device affinity in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specifies a name of a collection that represents the user device affinity in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DeviceId**

Specifies a device ID in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **DeviceName**

Specifies a device name in Configuration Manager.






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



#### **UserId**

Specifies a Configuration Manager ID for a user resource.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **UserName**

Specifies a user name for a resource in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject[]#SMS_UserMachineRelationship


* IResultObject#SMS_UserMachineRelationship






---


### Notes




---


### Syntax
```PowerShell
Get-CMUserDeviceAffinityRequest -CollectionId <String> [-DeviceId <String>] [-DeviceName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserId <String>] [-UserName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMUserDeviceAffinityRequest -CollectionName <String> [-DeviceId <String>] [-DeviceName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserId <String>] [-UserName <String>] [<CommonParameters>]
```
