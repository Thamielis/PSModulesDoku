Import-CMSecurityRole
---------------------




### Synopsis
Import a security role from an XML file.



---


### Description

Use this cmdlet to import a security role from an XML file. The XML was previously exported from Configuration Manager. You can use this export/import process to backup custom security roles, or copy them between separate hierarchies.



For example, you develop a custom security role in a lab environment. Export this new role from the lab hierarchy, and then import it into the production hierarchy.



For more information on security roles and permissions, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMSecurityRole](Copy-CMSecurityRole)



* [Export-CMSecurityRole](Export-CMSecurityRole)



* [Get-CMSecurityRole](Get-CMSecurityRole)



* [Remove-CMSecurityRole](Remove-CMSecurityRole)



* [Remove-CMSecurityRoleFromAdministrativeUser](Remove-CMSecurityRoleFromAdministrativeUser)



* [Set-CMSecurityRole](Set-CMSecurityRole)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Import a security role
```PowerShell
Import-CMSecurityRole -XmlFileName "RemoteAdminSecurity.xml" -Overwrite $True
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



#### **NewRoleName**

Specify the name for the new security role. If you specify `-Overwrite $false`, this value overrides the `RoleName` property in the XML file.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **Overwrite**

Set this parameter to `$true` to overwrite an existing security role with the same name.






|Type       |Required|Position|PipelineInput|Aliases           |
|-----------|--------|--------|-------------|------------------|
|`[Boolean]`|true    |named   |False        |OverwrittenExisted|



#### **XmlFileName**

Specify the path of the XML file to import the security role. It can be a local or network path. Include the `.xml` file extension.






|Type      |Required|Position|PipelineInput|Aliases                                                       |
|----------|--------|--------|-------------|--------------------------------------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>ImportFilePath<br/>Path<br/>RolesXml|



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
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Import-CMSecurityRole [-DisableWildcardHandling] [-ForceWildcardHandling] [-NewRoleName <String>] -Overwrite <Boolean> -XmlFileName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
