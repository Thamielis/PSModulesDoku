New-CMAdministrativeUserPermission
----------------------------------




### Synopsis
Create a permissions object to assign to an administrative user.



---


### Description

Use this cmdlet to create a permissions object to assign to an administrative user in Configuration Manager. Permissions can include security roles, security scopes, or collections. An administrative user in Configuration Manager defines a local or domain user or group. For more information about security roles, see Fundamentals of role-based administration in Configuration Manager (/mem/configmgr/core/understand/fundamentals-of-role-based-administration).



Use this permissions object with the New-CMAdministrativeUser (New-CMAdministrativeUser.md)cmdlet and its Permission parameter.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMAdministrativeUser](New-CMAdministrativeUser)



* [Automate role-based administration with Windows PowerShell](Automate role-based administration with Windows PowerShell)





---


### Examples
#### Example 1
```PowerShell
$accountName = "contoso\jqpublic"
$roleName = "Read-only Analyst"
$scopeName = "Scope1"
$collectionName = "All Systems"

$role = Get-CMSecurityRole -Name $roleName
$scope = Get-CMSecurityScope -Name $scopeName
$collection = Get-CMCollection -Name $collectionName

$perms = $role | New-CMAdministrativeUserPermission -RoleName $role.RoleName -SecurityScopeNames $scope.CategoryName -CollectionNames $collection.Name

$User = New-CMAdministrativeUser -Name $accountName -Permission $perms
$User.Permissions
```



---


### Parameters
#### **Collection**

Specify an array of collection objects to add to the permissions. To get this object, use the Get-CMCollection (Get-CMCollection.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases    |
|-------------------|--------|--------|-------------|-----------|
|`[IResultObject[]]`|false   |named   |False        |Collections|



#### **CollectionId**

Specify an array of collection IDs to add to the permissions. This value is the CollectionID property, for example, `SMS00001`.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|false   |named   |False        |CollectionIds|



#### **CollectionName**

Specify an array of collection names to add to the permissions.






|Type        |Required|Position|PipelineInput|Aliases        |
|------------|--------|--------|-------------|---------------|
|`[String[]]`|false   |named   |False        |CollectionNames|



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

Specify a security role object to add to the permissions. To get this object, use the Get-CMSecurityRole (Get-CMSecurityRole.md)cmdlet.






|Type             |Required|Position|PipelineInput |Aliases|
|-----------------|--------|--------|--------------|-------|
|`[IResultObject]`|true    |named   |True (ByValue)|Role   |



#### **RoleId**

Specify the ID of a security role to add to the permissions. This value is the `RoleID` property, for example `SMS000AR` for the OS Deployment Manager role.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **RoleName**

Specify the name of a security role to add to the permissions.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **SecurityScope**

Specify a security scope object to add to the permissions. To get this object, use the Get-CMSecurityScope (Get-CMSecurityScope.md)cmdlet.






|Type               |Required|Position|PipelineInput|Aliases       |
|-------------------|--------|--------|-------------|--------------|
|`[IResultObject[]]`|false   |named   |False        |SecurityScopes|



#### **SecurityScopeId**

Specify the ID of a security scope to add to the permissions. This value is the `CategoryID` property, for example `SMS00UNA` for the Default scope.






|Type        |Required|Position|PipelineInput|Aliases         |
|------------|--------|--------|-------------|----------------|
|`[String[]]`|false   |named   |False        |SecurityScopeIds|



#### **SecurityScopeName**

Specify the name of a security scope to add to the permissions.






|Type        |Required|Position|PipelineInput|Aliases           |
|------------|--------|--------|-------------|------------------|
|`[String[]]`|false   |named   |False        |SecurityScopeNames|





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject#SMS_APermission






---


### Notes
For more information on this return object and its properties, see SMS_APermission server WMI class (/mem/configmgr/develop/reference/core/servers/configure/sms_apermission-server-wmi-class).



---


### Syntax
```PowerShell
New-CMAdministrativeUserPermission [-Collection <IResultObject[]>] [-CollectionId <String[]>] [-CollectionName <String[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-SecurityScope <IResultObject[]>] [-SecurityScopeId <String[]>] [-SecurityScopeName <String[]>] [<CommonParameters>]
```
```PowerShell
New-CMAdministrativeUserPermission [-Collection <IResultObject[]>] [-CollectionId <String[]>] [-CollectionName <String[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -RoleId <String> [-SecurityScope <IResultObject[]>] [-SecurityScopeId <String[]>] [-SecurityScopeName <String[]>] [<CommonParameters>]
```
```PowerShell
New-CMAdministrativeUserPermission [-Collection <IResultObject[]>] [-CollectionId <String[]>] [-CollectionName <String[]>] [-DisableWildcardHandling] [-ForceWildcardHandling] -RoleName <String> [-SecurityScope <IResultObject[]>] [-SecurityScopeId <String[]>] [-SecurityScopeName <String[]>] [<CommonParameters>]
```
