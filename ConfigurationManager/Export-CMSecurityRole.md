Export-CMSecurityRole
---------------------




### Synopsis
Export a security role to an XML file.



---


### Description

Use this cmdlet to export the configuration of a custom security role from the site to an XML file. You can't export built-in roles. For more information on security roles and permissions, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMSecurityRole](Copy-CMSecurityRole)



* [Get-CMSecurityRole](Get-CMSecurityRole)



* [Import-CMSecurityRole](Import-CMSecurityRole)



* [Set-CMSecurityRole](Set-CMSecurityRole)



* [Remove-CMSecurityRole](Remove-CMSecurityRole)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Export a custom security role
```PowerShell
Export-CMSecurityRole -Path "\\Contoso01\Export\Sec_Roles\Security_Manager.xml" -RoleId "XYZ00001"
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



#### **InputObject**

Specify a security role object to export. To get this object, use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Role   |



#### **Path**

Specify the path of the XML file to export the security role. It can be a local or network path. Include the `.xml` file extension.






|Type      |Required|Position|PipelineInput|Aliases                                                              |
|----------|--------|--------|-------------|---------------------------------------------------------------------|
|`[String]`|true    |named   |False        |FileName<br/>FilePath<br/>ExportFilePath<br/>XmlFileName<br/>RolesXml|



#### **RoleId**

Specify the ID of the security role to export. This value is the `RoleID` property. Since this cmdlet only works with custom roles, this value should always start with the site code. (IDs for built-in roles start with `SMS`.)






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RoleName**

Specify the name of the security role to export.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Export-CMSecurityRole [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -Path <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMSecurityRole [-DisableWildcardHandling] [-ForceWildcardHandling] -Path <String> -RoleId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Export-CMSecurityRole [-DisableWildcardHandling] [-ForceWildcardHandling] -Path <String> -RoleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
