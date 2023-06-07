Remove-CMCollectionDirectMembershipRule
---------------------------------------




### Synopsis
Remove a direct membership rule from a device or user collection.



---


### Description

Use this cmdlet to remove a direct membership rule from a device or user collection. A direct membership rule lets you explicitly choose the members of the collection. Default collections don't have direct membership rules. Any collection that you target should have an ID that starts with the site code, not `SMS`. For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



When you remove a direct membership rule from a collection, the resource may no longer be a member of the collection. This action can cause any software or configuration deployment to not apply to the resource.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMCollectionDirectMembershipRule](Get-CMCollectionDirectMembershipRule)



* [Remove-CMCollectionExcludeMembershipRule](Remove-CMCollectionExcludeMembershipRule)



* [Remove-CMCollectionIncludeMembershipRule](Remove-CMCollectionIncludeMembershipRule)



* [Remove-CMCollectionQueryMembershipRule](Remove-CMCollectionQueryMembershipRule)



* [Add-CMDeviceCollectionDirectMembershipRule](Add-CMDeviceCollectionDirectMembershipRule)



* [Add-CMUserCollectionDirectMembershipRule](Add-CMUserCollectionDirectMembershipRule)



* [Get-CMDeviceCollectionDirectMembershipRule](Get-CMDeviceCollectionDirectMembershipRule)



* [Get-CMUserCollectionDirectMembershipRule](Get-CMUserCollectionDirectMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Get-CMResource](Get-CMResource)



* [Get-CMDevice](Get-CMDevice)



* [Get-CMUser](Get-CMUser)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Remove the local machine from a collection of test devices
```PowerShell
Remove-CMCollectionDirectMembershipRule -CollectionName 'Test Devices' -ResourceName $env:ComputerName -Force
```



---


### Parameters
#### **CollectionId**

Specify the ID of the collection with the direct rule to remove. For example, `"XYZ0003F"`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the collection with the direct rule to remove.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a collection object with the direct rule to remove. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **Resource**

Specify an array of resource objects to remove from the collection. To get this object, use the Get-CMResource (Get-CMResource.md), [Get-CMDevice](Get-CMDevice.md), or [Get-CMUser](Get-CMUser.md)cmdlets.






|Type               |Required|Position|PipelineInput|Aliases  |
|-------------------|--------|--------|-------------|---------|
|`[IResultObject[]]`|true    |named   |False        |Resources|



#### **ResourceId**

Specify an array of resource IDs to remove from the collection. This value is the ResourceId property of the SMS_Resource class. For example, `"33555693"`.






|Type        |Required|Position|PipelineInput|Aliases    |
|------------|--------|--------|-------------|-----------|
|`[String[]]`|true    |named   |False        |ResourceIds|



#### **ResourceName**

Specify an array of resource names to remove from the collection.






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
This cmdlet is similar to Remove-CMDeviceCollectionDirectMembershipRule and Remove-CMUserCollectionDirectMembershipRule , which are specific to the type of collection. This cmdlet works with either device or user collections.



---


### Syntax
```PowerShell
Remove-CMCollectionDirectMembershipRule -CollectionId <String> [-Force] -Resource <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionDirectMembershipRule -CollectionId <String> [-Force] -ResourceId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionDirectMembershipRule -CollectionId <String> [-Force] -ResourceName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionDirectMembershipRule -CollectionName <String> [-Force] -ResourceName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionDirectMembershipRule -CollectionName <String> [-Force] -Resource <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionDirectMembershipRule -CollectionName <String> [-Force] -ResourceId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionDirectMembershipRule [-Force] -InputObject <IResultObject> -Resource <IResultObject[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionDirectMembershipRule [-Force] -InputObject <IResultObject> -ResourceId <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMCollectionDirectMembershipRule [-Force] -InputObject <IResultObject> -ResourceName <String[]> [-Confirm] [-WhatIf] [<CommonParameters>]
```
