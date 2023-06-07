Get-CMObjectSecurityScope
-------------------------




### Synopsis
Get the security scope for an object.



---


### Description

Use this cmdlet to get the security scopes that are associated with a Configuration Manager object.



For more information on security scopes, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMObjectSecurityScope](Add-CMObjectSecurityScope)



* [Remove-CMObjectSecurityScope](Remove-CMObjectSecurityScope)



* [Get-CMSecurityScope](Get-CMSecurityScope)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1: Get security scopes for an application
```PowerShell
Get-CMApplication -Name "Central app" | Get-CMObjectSecurityScope
```

#### Example 2: Get a security scope for a package
```PowerShell
$pkg = Get-CMPackage -Id "XYZ00001"
Get-CMObjectSecurityScope -InputObject $pkg -Name "Scope1"
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

Specify the ID of a security scope that's associated with a Configuration Manager object. This value is the `CategoryID` property, for example `SMS00UNA` for the Default scope.






|Type      |Required|Position|PipelineInput|Aliases   |
|----------|--------|--------|-------------|----------|
|`[String]`|false   |named   |False        |CategoryId|



#### **InputObject**

Specify a Configuration Manager object that's associated with a security scope. To get this object, use the Get cmdlet for the object type. For example, Get-CMApplication for app objects.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a security scope that's associated with a Configuration Manager object.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |CategoryName|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_SecuredCategory


* IResultObject#SMS_SecuredCategory






---


### Notes
For more information on this return object and its properties, see SMS_SecuredCategory server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_securedcategory-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMObjectSecurityScope [-DisableWildcardHandling] [-ForceWildcardHandling] [-Id <String>] -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMObjectSecurityScope [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Name <String>] [<CommonParameters>]
```
