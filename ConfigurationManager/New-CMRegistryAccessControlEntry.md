New-CMRegistryAccessControlEntry
--------------------------------




### Synopsis
Create a registry key access control entry.



---


### Description

Use this cmdlet to create an access control entry (ACE) for a registry key. An access control entry defines specific permissions for a specific user or group. You can use this object with the New-CMRequirementRuleRegistryKeyPermissionValue cmdlet to create a requirement rule on an application deployment type that verifies registry key permissions.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMRequirementRuleRegistryKeyPermissionValue](New-CMRequirementRuleRegistryKeyPermissionValue)





---


### Examples
#### Example 1: Add a requirement rule for registry key permissions
```PowerShell
$myGC = Get-CMGlobalCondition -Name "LOB app registry key"

$userName = "contoso\jqpublic"
$ce = New-CMRegistryAccessControlEntry -GroupOrUserName $userName -AccessOption Allow -Permission Read,Write

$userName2 = "contoso\jdoe"
$ce2 = New-CMRegistryAccessControlEntry -GroupOrUserName $userName2 -AccessOption Allow -Permission Read

$myRule = $myGC | New-CMRequirementRuleRegistryKeyPermissionValue -Exclusive $false -ControlEntry $ce,$ce2

Set-CMScriptDeploymentType -ApplicationName "Central app" -DeploymentTypeName "Install" -AddRequirement $myRule
```



---


### Parameters
#### **AccessOption**

Specify whether this ACE is to `Allow` or `Deny` access.



Valid Values:

* Allow
* Deny






|Type          |Required|Position|PipelineInput|
|--------------|--------|--------|-------------|
|`[AccessType]`|false   |named   |False        |



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



#### **GroupOrUserName**

Specify the group or user name for this ACE. Use standard "domain\name" format. For example, `contoso\jqpublic` or `"nwtraders\All IT Users"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Permission**

Specify an array of one or more permissions for this ACE. Use the AccessOption parameter to specify whether these permissions `Allow` or `Deny` access.



Valid Values:

* ChangePermissions
* CreateLink
* CreateSubkey
* Delete
* EnumerateSubkeys
* FullControl
* Notify
* QueryValue
* Read
* ReadPermissions
* SetValue
* TakeOwnership
* Write






|Type                     |Required|Position|PipelineInput|Aliases    |
|-------------------------|--------|--------|-------------|-----------|
|`[RegistryPermissions[]]`|false   |named   |False        |Permissions|





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
New-CMRegistryAccessControlEntry [-AccessOption {Allow | Deny}] [-DisableWildcardHandling] [-ForceWildcardHandling] -GroupOrUserName <String> [-Permission {ChangePermissions | CreateLink | CreateSubkey | Delete | EnumerateSubkeys | FullControl | Notify | QueryValue | Read | ReadPermissions | SetValue | TakeOwnership | Write}] [<CommonParameters>]
```
