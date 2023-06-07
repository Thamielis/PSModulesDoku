Remove-CMUserCollectionIncludeMembershipRule
--------------------------------------------




### Synopsis
Remove an include membership rule from a user collection.



---


### Description

Use this cmdlet to remove an include membership rule from a user collection. An include membership rule includes the members of another collection in the user collections where the rule is applied.



For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



When you remove an include membership rule to a collection, a resource may no longer be a member of the user collection. This action can cause any software or configuration deployment to not apply to a user.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMUserCollectionIncludeMembershipRule](Add-CMUserCollectionIncludeMembershipRule)



* [Get-CMUserCollectionIncludeMembershipRule](Get-CMUserCollectionIncludeMembershipRule)



* [Remove-CMCollectionIncludeMembershipRule](Remove-CMCollectionIncludeMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Remove-CMDeviceCollectionIncludeMembershipRule](Remove-CMDeviceCollectionIncludeMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Remove an include membership rule
```PowerShell
Remove-CMUserCollectionIncludeMembershipRule -CollectionName "Users" -IncludeCollectionName "All Users" -Force
```



---


### Parameters
#### **CollectionId**

Specify the ID of the user collection to remove the rule. This value is the CollectionID property, for example, `XYZ00012`. Since default collections don't have include membership rules, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the user collection to remove the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **IncludeCollection**

Specify an object for the included collection to remove the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **IncludeCollectionId**

Specify the ID of the included collection to remove the rule. This value is the CollectionID property, for example, `XYZ00012`. You can include default collections, so this value can start with either the site code or `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **IncludeCollectionName**

Specify the name of the included collection to remove the rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specify an object for the user collection to remove the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



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
Remove-CMUserCollectionIncludeMembershipRule -CollectionId <String> [-Force] -IncludeCollection <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionIncludeMembershipRule -CollectionId <String> [-Force] -IncludeCollectionId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionIncludeMembershipRule -CollectionId <String> [-Force] -IncludeCollectionName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionIncludeMembershipRule -CollectionName <String> [-Force] -IncludeCollectionName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionIncludeMembershipRule -CollectionName <String> [-Force] -IncludeCollection <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionIncludeMembershipRule -CollectionName <String> [-Force] -IncludeCollectionId <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionIncludeMembershipRule [-Force] -IncludeCollection <IResultObject> -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionIncludeMembershipRule [-Force] -IncludeCollectionId <String> -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionIncludeMembershipRule [-Force] -IncludeCollectionName <String> -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
