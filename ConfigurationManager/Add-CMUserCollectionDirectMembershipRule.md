Add-CMUserCollectionDirectMembershipRule
----------------------------------------




### Synopsis
Add a direct membership rule to a user collection.



---


### Description

Use this cmdlet to add a direct membership rule to a user collection. A direct membership rule lets you explicitly choose the members of the user collection. You can't add membership rules to default collections. Any collection that you target should have an ID that starts with the site code, not `SMS`. For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMUserCollectionDirectMembershipRule](Get-CMUserCollectionDirectMembershipRule)



* [Remove-CMUserCollectionDirectMembershipRule](Remove-CMUserCollectionDirectMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Get-CMResource](Get-CMResource)



* [Get-CMUser](Get-CMUser)



* [Add-CMDeviceCollectionDirectMembershipRule](Add-CMDeviceCollectionDirectMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Add a direct membership rule to a user collection
```PowerShell
Add-CMUserCollectionDirectMembershipRule -CollectionId "XYZ00057" -ResourceId "16777210"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the user collection to add the rule. This value is the CollectionID property, for example, `XYZ00012`. Since you can't add membership rules to default collections, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify the name of the user collection to add the rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specify an object for the user collection to add the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Resource**

Specify an array of resource objects to add to the user collection with this direct membership rule. To get this object, use the Get-CMResource (Get-CMResource.md) or [Get-CMUser](Get-CMUser.md)cmdlets.






|Type               |Required|Position|PipelineInput |Aliases  |
|-------------------|--------|--------|--------------|---------|
|`[IResultObject[]]`|true    |named   |True (ByValue)|Resources|



#### **ResourceId**

Specify an array of IDs of the resources to add to the user collection with this direct membership rule. This value is the ResourceID property, for example `16777219`.






|Type       |Required|Position|PipelineInput|Aliases    |
|-----------|--------|--------|-------------|-----------|
|`[Int32[]]`|true    |named   |False        |ResourceIds|



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



Microsoft.ConfigurationManagement.ManagementProvider.IResultObject[]





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes




---


### Syntax
```PowerShell
Add-CMUserCollectionDirectMembershipRule -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -ResourceId <Int32[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionDirectMembershipRule -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -Resource <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionDirectMembershipRule -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -ResourceId <Int32[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionDirectMembershipRule -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-PassThru] -Resource <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionDirectMembershipRule [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] -Resource <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMUserCollectionDirectMembershipRule [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] -ResourceId <Int32[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
