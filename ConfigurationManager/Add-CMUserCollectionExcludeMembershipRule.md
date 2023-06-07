Add-CMUserCollectionExcludeMembershipRule
-----------------------------------------




### Synopsis
Add an exclude membership rule to a user collection.



---


### Description

Use this cmdlet to add an exclude membership rule to a user collection. An exclude membership rule excludes the members of another collection from the user collections where the rule is applied.



You can't add membership rules to default collections. Any collection that you target should have an ID that starts with the site code, not `SMS`. You can exclude a default collection, so the ID of an excluded collection can start with `SMS`.



Configuration Manager dynamically updates the membership of the user collection on a schedule if the membership of the excluded collection changes.



When you add an exclude membership rule to a collection, a resource may no longer be a member of the user collection. This action can cause any software or configuration deployment to not apply to a user.



For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMUserCollectionExcludeMembershipRule](Get-CMUserCollectionExcludeMembershipRule)



* [Remove-CMUserCollectionExcludeMembershipRule](Remove-CMUserCollectionExcludeMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Add-CMDeviceCollectionExcludeMembershipRule](Add-CMDeviceCollectionExcludeMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Add an exclude collection rule to a user collection
```PowerShell
Add-CMUserCollectionExcludeMembershipRule -CollectionId "XYZ00012" -ExcludeCollectionId "XYZ00017"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the user collection to add the rule. This value is the CollectionID property, for example, `XYZ00012`. Since default collections don't have exclude membership rules, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the user collection to add the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **ExcludeCollection**

Specify an object for the excluded collection to add the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ExcludeCollectionId**

Specify the ID of the excluded collection to add the rule. This value is the CollectionID property, for example, `XYZ00012`. You can exclude default collections, so this value can start with either the site code or `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ExcludeCollectionName**

Specify the name of the excluded collection to add the rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specify an object for the user collection to add the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



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
Add-CMUserCollectionExcludeMembershipRule -CollectionId <String> -ExcludeCollection <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionExcludeMembershipRule -CollectionId <String> -ExcludeCollectionId <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionExcludeMembershipRule -CollectionId <String> -ExcludeCollectionName <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionExcludeMembershipRule -CollectionName <String> -ExcludeCollectionName <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionExcludeMembershipRule -CollectionName <String> -ExcludeCollection <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionExcludeMembershipRule -CollectionName <String> -ExcludeCollectionId <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionExcludeMembershipRule -ExcludeCollection <IResultObject> -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionExcludeMembershipRule -ExcludeCollectionId <String> -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionExcludeMembershipRule -ExcludeCollectionName <String> -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
