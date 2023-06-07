Set-CMSecurityRolePermission
----------------------------




### Synopsis
Configure a security role with specific permissions.



---


### Description

Use this cmdlet to configure a security role with specific permissions. For more information on security roles and permissions, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSecurityRolePermission](Get-CMSecurityRolePermission)



* [Get-CMSecurityRole](Get-CMSecurityRole)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1
```PowerShell
$roleName = "Contoso custom role"
$role = Get-CMSecurityRole -Name $roleName

$ops = @{
  Boundaries = "Create,Delete";
  Application="Read";
  "Alert Subscription"="Modify,Set Security Scope"
}

$role | Set-CMSecurityRolePermission -RolePermission $ops
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

Specify the ID of the security role to configure its permissions. This value is the `RoleID` property, for example `SMS000AR` for the OS Deployment Manager role.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |RoleId |



#### **InputObject**

Specify a security role object to configure its permissions. To get this object, use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases     |
|-----------------|--------|--------|--------------|------------|
|`[IResultObject]`|true    |named   |True (ByValue)|SecurityRole|



#### **Name**

Specify the name of the security role to configure its permissions.






|Type      |Required|Position|PipelineInput|Aliases |
|----------|--------|--------|-------------|--------|
|`[String]`|true    |named   |False        |RoleName|



#### **RolePermission**

Specify a hashtable (/powershell/module/microsoft.powershell.core/about/about_hash_tables)of allowed operations, or permissions, for the target role. The first value of the hashtable is the class name, and the second value is an array of permission names.


For an example, see Example 1 (#examples).






|Type         |Required|Position|PipelineInput|
|-------------|--------|--------|-------------|
|`[Hashtable]`|true    |named   |False        |



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
Set-CMSecurityRolePermission [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> -RolePermission <Hashtable> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSecurityRolePermission [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -RolePermission <Hashtable> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSecurityRolePermission [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> -RolePermission <Hashtable> [-Confirm] [-WhatIf] [<CommonParameters>]
```
