Set-CMSecurityRole
------------------




### Synopsis
Configure a security role.



---


### Description

Use this cmdlet to change the configuration settings of a custom security role. You can't configure built-in roles.



For more information on security roles and permissions, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMSecurityRole](Copy-CMSecurityRole)



* [Export-CMSecurityRole](Export-CMSecurityRole)



* [Get-CMSecurityRole](Get-CMSecurityRole)



* [Import-CMSecurityRole](Import-CMSecurityRole)



* [Remove-CMSecurityRole](Remove-CMSecurityRole)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Rename a security role
```PowerShell
Set-CMSecurityRole -Id "CM100003" -NewName "RTOperator02"
```



---


### Parameters
#### **Description**

Specify an optional description for the security role.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |named   |False        |RoleDescription|



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

Specify the ID of the custom security role to configure. This value is the `RoleID` property. Since this cmdlet only works with custom roles, this value should always start with the site code. (IDs for built-in roles start with `SMS`.)






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |RoleId |



#### **InputObject**

Specify a custom security role object to configure. To get this object, use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of the custom security role to configure.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |RoleName|



#### **NewName**

Specify a new name for the custom security role.






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
Set-CMSecurityRole [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSecurityRole [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSecurityRole [-Description <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-Confirm] [-WhatIf] [<CommonParameters>]
```