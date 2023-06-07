Remove-CMUserCollectionExcludeMembershipRule
--------------------------------------------




### Synopsis
Remove an exclude membership rule from a user collection.



---


### Description

Use this cmdlet to remove an exclude membership rule from a user collection. An exclude membership rule excludes the members of another collection from the user collections where the rule is applied.



For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



When you remove an exclude membership rule from a collection, resources may become members of the collection. This action can cause any software or configuration deployment to apply to users in the previously excluded collection.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMUserCollectionExcludeMembershipRule](Add-CMUserCollectionExcludeMembershipRule)



* [Get-CMUserCollectionExcludeMembershipRule](Get-CMUserCollectionExcludeMembershipRule)



* [Remove-CMCollectionExcludeMembershipRule](Remove-CMCollectionExcludeMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Remove-CMDeviceCollectionExcludeMembershipRule](Remove-CMDeviceCollectionExcludeMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Remove an exclude membership rule from a user collection
```PowerShell
Remove-CMUserCollectionExcludeMembershipRule -CollectionId "XYZ00012" -ExcludeCollectionId "XYZ00089" -Force
```



---


### Parameters
#### **CollectionId**

Specify the ID of the user collection to remove the rule. This value is the CollectionID property, for example, `XYZ00012`. Since default collections don't have exclude membership rules, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the user collection to remove the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **ExcludeCollection**

Specify an object for the excluded collection to remove the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ExcludeCollectionId**

Specify the ID of the excluded collection to remove the rule. This value is the CollectionID property, for example, `XYZ00012`. You can exclude default collections, so this value can start with either the site code or `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ExcludeCollectionName**

Specify the name of the excluded collection to get the rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Remove-CMUserCollectionExcludeMembershipRule -CollectionId <String> -ExcludeCollection <IResultObject> [-Force] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionExcludeMembershipRule -CollectionId <String> -ExcludeCollectionId <String> [-Force] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionExcludeMembershipRule -CollectionId <String> -ExcludeCollectionName <String> [-Force] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionExcludeMembershipRule -CollectionName <String> -ExcludeCollectionName <String> [-Force] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionExcludeMembershipRule -CollectionName <String> -ExcludeCollection <IResultObject> [-Force] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionExcludeMembershipRule -CollectionName <String> -ExcludeCollectionId <String> [-Force] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionExcludeMembershipRule -ExcludeCollection <IResultObject> [-Force] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionExcludeMembershipRule -ExcludeCollectionId <String> [-Force] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionExcludeMembershipRule -ExcludeCollectionName <String> [-Force] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
