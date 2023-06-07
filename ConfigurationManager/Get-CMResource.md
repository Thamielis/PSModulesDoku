Get-CMResource
--------------




### Synopsis
Get a Configuration Manager resource.



---


### Description

The Get-CMResource cmdlet gets a Configuration Manager resource, such as a device or a user.



For more complete data, use Get-CMDevice (Get-CMDevice.md) or [Get-CMUser](Get-CMUser.md). For devices, it queries the SMS_R_System class. If you use `Get-CMDevice -Resource` the output is the same as Get-CMResource .



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMResource](Remove-CMResource)



* [Get-CMDevice](Get-CMDevice)



* [Get-CMUser](Get-CMUser)





---


### Examples
#### Example 1: Get a resource by ID
```PowerShell
Get-CMResource -ResourceID "2097152000" -Fast
```

#### Example 2: Get all user resources
```PowerShell
Get-CMResource -ResourceType User
```



---


### Parameters
#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Fast**

Add this parameter to not automatically refresh lazy properties. Lazy properties contain values that are relatively inefficient to retrieve. Getting these properties can cause additional network traffic and decrease cmdlet performance.


If you don't use this parameter, the cmdlet displays a warning. To disable this warning, set `$CMPSSuppressFastNotUsedCheck = $true`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **ResourceId**

Specifies the ID of a resource. For example, `16780010`.






|Type     |Required|Position|PipelineInput|Aliases|
|---------|--------|--------|-------------|-------|
|`[Int32]`|false   |0       |False        |Id     |



#### **ResourceType**

Specifies the resource type.



Valid Values:

* None
* UnknownResource
* UserGroup
* User
* System






|Type            |Required|Position|PipelineInput|
|----------------|--------|--------|-------------|
|`[ResourceType]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* IResultObject#SMS_Resource






---


### Notes




---


### Syntax
```PowerShell
Get-CMResource [[-ResourceId] <Int32>] [-DisableWildcardHandling] [-Fast] [-ForceWildcardHandling] [-ResourceType {None | UnknownResource | UserGroup | User | System}] [<CommonParameters>]
```
