Set-CMCollectionCloudSync
-------------------------




### Synopsis
Configure collection membership synchronization to Azure Active Directory groups for a device or user collection. For more information, see How to synchronize collection members to Azure AD groups (/mem/configmgr/core/clients/manage/collections/synchronize-collections-aad-group)



---


### Description

Use this cmdlet to configure collection membership synchronization to Azure Active Directory groups for a device or user collection.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Get-CMAADTenant](Get-CMAADTenant)



* [How to synchronize collection members to Azure AD groups](How to synchronize collection members to Azure AD groups)





---


### Examples
#### Example 1: Enable a collection to synchronize members to Azure AD group
```PowerShell
$userCollection = Get-CMCollection -Name "testUserCollection"
$AADTenant = Get-CMAADTenant -Name "contoso"
Set-CMCollectionCloudSync -InputObject $userCollection -AddGroupName "testUserGroup" -EnableAssignEndpointSecurityPolicy $true -TenantObject $AADTenant
```

#### Example 2: Remove collection synchronization with Azure AD group
```PowerShell
$userCollection = Get-CMCollection -Name "testUserCollection"
Set-CMCollectionCloudSync -InputObject $userCollection -RemoveGroupName "testUserGroup" -EnableAssignEndpointSecurityPolicy $true -TenantName "contoso"
```



---


### Parameters
#### **AADGroupName**

Specify target Azure Active Directory group name with which the collection's members needs to be synchronized.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **EnableAssignEndpointSecurityPolicy**

Use this parameter enable or disable the collection to show up in Intune portal to assign endpoint security policies in Tenant Attach scenario.






|Type       |Required|Position|PipelineInput|
|-----------|--------|--------|-------------|
|`[Boolean]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the collection to configure. This value is the CollectionID property, for example, `XYZ00012`.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CollectionId|



#### **InputObject**

Specify a collection object to configure. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **Name**

Specify the name of a collection to configure.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |CollectionName|



#### **RemoveGroupName**

Use this parameter to remove synchronization with the specified Azure Active Directory group.






|Type      |Required|Position|PipelineInput|Aliases         |
|----------|--------|--------|-------------|----------------|
|`[String]`|false   |named   |False        |RemoveGroupNames|



#### **TenantId**

Specify the ID of the Azure Active Directory tenant. This value is the TenantId property, for example, `72f988bf-00ab-11cd-22ef-2d7cd011db00`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TenantName**

Specify the name of the Azure Active Directory tenant, for example, `contoso`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **TenantObject**

Specify an object for the Azure Active Directory tenant. To get this object, use the Get-CMAADTenant (Get-CMAADTenant.md)cmdlet.






|Type             |Required|Position|PipelineInput|Aliases|
|-----------------|--------|--------|-------------|-------|
|`[IResultObject]`|true    |named   |False        |Tenant |



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
Set-CMCollectionCloudSync -AADGroupName <String> [-DisableWildcardHandling] [-EnableAssignEndpointSecurityPolicy <Boolean>] [-ForceWildcardHandling] -Id <String> [-RemoveGroupName <String>] -TenantId <String> -TenantName <String> -TenantObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionCloudSync -AADGroupName <String> [-DisableWildcardHandling] [-EnableAssignEndpointSecurityPolicy <Boolean>] [-ForceWildcardHandling] -InputObject <IResultObject> [-RemoveGroupName <String>] -TenantId <String> -TenantName <String> -TenantObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollectionCloudSync -AADGroupName <String> [-DisableWildcardHandling] [-EnableAssignEndpointSecurityPolicy <Boolean>] [-ForceWildcardHandling] -Name <String> [-RemoveGroupName <String>] -TenantId <String> -TenantName <String> -TenantObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
