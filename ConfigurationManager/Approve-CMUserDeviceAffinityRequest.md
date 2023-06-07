Approve-CMUserDeviceAffinityRequest
-----------------------------------




### Synopsis
Approves a request for user device affinity in Configuration Manager.



---


### Description

The Approve-CMUserDeviceAffinityRequest cmdlet approves a request for user device affinity.



In Configuration Manager, user device affinity defines a relationship between a user and a device. Instead of deploying an application to a group of devices, you deploy an application to a user and Configuration Manager installs the application on all devices associated with the user.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Deny-CMUserDeviceAffinityRequest](Deny-CMUserDeviceAffinityRequest)



* [Get-CMUserDeviceAffinityRequest](Get-CMUserDeviceAffinityRequest)





---


### Examples
#### Example 1: Approve a request for user device affinity
```PowerShell
PS XYZ:\>Approve-CMUserDeviceAffinityRequest -CollectionName "All Systems" -UserName "Western\EvanNarvaez$"
```
This command approves a request for user device affinity for the collection named All Systems.


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



#### **UserDeviceAffinityRequest**

Specifies a CMUserDeviceAffinityRequest object. To obtain a CMUserDeviceAffinityRequest object, use the Get-CMUserDeviceAffinityRequest (Get-CMUserDeviceAffinityRequest.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|false   |named   |True (ByValue)|



#### **UserDeviceAffinityRequestId**

Specifies a unique ID for a request for user device affinity.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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
Approve-CMUserDeviceAffinityRequest -CollectionId <String> [-DeviceId <String>] [-DeviceName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserDeviceAffinityRequest <IResultObject>] [-UserDeviceAffinityRequestId <String>] [-UserId <String>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Approve-CMUserDeviceAffinityRequest -CollectionName <String> [-DeviceId <String>] [-DeviceName <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-UserDeviceAffinityRequest <IResultObject>] [-UserDeviceAffinityRequestId <String>] [-UserId <String>] [-UserName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
