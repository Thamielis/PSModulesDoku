Remove-CMUserCollectionDirectMembershipRule
-------------------------------------------




### Synopsis
Remove a direct membership rule from a user collection.



---


### Description

Use this cmdlet to remove a direct membership rule from a user collection. A direct membership rule lets you explicitly choose the members of the user collection. Default collections don't have direct membership rules. Any collection that you target should have an ID that starts with the site code, not `SMS`. For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



When you remove a direct membership rule from a collection, the resource may no longer be a member of the collection. This action can cause any software or configuration deployment to not apply to the user.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMUserCollectionDirectMembershipRule](Add-CMUserCollectionDirectMembershipRule)



* [Get-CMUserCollectionDirectMembershipRule](Get-CMUserCollectionDirectMembershipRule)



* [Remove-CMCollectionDirectMembershipRule](Remove-CMCollectionDirectMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Get-CMResource](Get-CMResource)



* [Get-CMUser](Get-CMUser)



* [Remove-CMDeviceCollectionDirectMembershipRule](Remove-CMDeviceCollectionDirectMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Remove a direct membership rule from a user collection
```PowerShell
Remove-CMUserCollectionDirectMembershipRule -CollectionID "XYZ0001A" -ResourceId "33555693"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the user collection with the direct rule to remove. For example, `"XYZ0003F"`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the user collection with the direct rule to remove.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a user collection object with the direct rule to remove. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **Resource**

Specify an array of resource objects to remove from the user collection. To get this object, use the Get-CMResource (Get-CMResource.md) or [Get-CMUser](Get-CMUser.md)cmdlets.






|Type               |Required|Position|PipelineInput|Aliases  |
|-------------------|--------|--------|-------------|---------|
|`[IResultObject[]]`|true    |named   |False        |Resources|



#### **ResourceId**

Specify an array of resource IDs to remove from the user collection. This value is the ResourceId property of the SMS_Resource class. For example, `"33555693"`.






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|true    |named   |False        |ResourceIds|



#### **ResourceName**

Specify an array of resource names to remove the direct membership rules from the user collection.






|Type        |Required|Position|PipelineInput|Aliases      |
|------------|--------|--------|-------------|-------------|
|`[String[]]`|true    |named   |False        |ResourceNames|



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
Remove-CMUserCollectionDirectMembershipRule -CollectionId <String> [-Force] -Resource <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionDirectMembershipRule -CollectionId <String> [-Force] -ResourceId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionDirectMembershipRule -CollectionId <String> [-Force] -ResourceName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionDirectMembershipRule -CollectionName <String> [-Force] -ResourceName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionDirectMembershipRule -CollectionName <String> [-Force] -Resource <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionDirectMembershipRule -CollectionName <String> [-Force] -ResourceId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionDirectMembershipRule [-Force] -InputObject <IResultObject> -Resource <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionDirectMembershipRule [-Force] -InputObject <IResultObject> -ResourceId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMUserCollectionDirectMembershipRule [-Force] -InputObject <IResultObject> -ResourceName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
