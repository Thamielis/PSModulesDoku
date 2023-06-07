Get-CMCollectionDirectMembershipRule
------------------------------------




### Synopsis
Get a direct membership rule for a device or user collection.



---


### Description

Use this cmdlet to get one or more direct membership rules for a device or user collection. A direct membership rule lets you explicitly choose the members of the device collection. Default collections don't have direct membership rules. Any collection that you target should have an ID that starts with the site code, not `SMS`. For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Remove-CMCollectionDirectMembershipRule](Remove-CMCollectionDirectMembershipRule)



* [Get-CMCollectionExcludeMembershipRule](Get-CMCollectionExcludeMembershipRule)



* [Get-CMCollectionIncludeMembershipRule](Get-CMCollectionIncludeMembershipRule)



* [Get-CMCollectionQueryMembershipRule](Get-CMCollectionQueryMembershipRule)



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
#### Example 1: Get all direct membership rules for a collection by name
```PowerShell
Get-CMCollectionDirectMembershipRule -CollectionName "Device01"
```

#### Example 2: Get all direct membership rules by using the pipeline
```PowerShell
Get-CMCollection -Name "User02" | Get-CMCollectionDirectMembershipRule
```



---


### Parameters
#### **CollectionId**

Specify the ID of the collection to get the rule. This value is the CollectionID property, for example, `XYZ00012`. Since default collections can't have direct membership rules, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the collection to get the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **InputObject**

Specify an object for the collection to get the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **Resource**

Specify a resource, device, or user object to get its direct membership rule from the collection. To get this object, use the Get-CMResource (Get-CMResource.md), [Get-CMDevice](Get-CMDevice.md), or [Get-CMUser](Get-CMUser.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **ResourceId**

Specify the ID of the resource to get its direct membership rule from the collection. This value is the ResourceID property, for example `16777219`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ResourceName**

Specify the name of the device or user to get its direct membership rule from the collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes
This cmdlet is similar to Get-CMDeviceCollectionDirectMembershipRule and Get-CMUserCollectionDirectMembershipRule , which are specific to the type of collection. This cmdlet works with either device or user collections.



---


### Syntax
```PowerShell
Get-CMCollectionDirectMembershipRule -CollectionId <String> -Resource <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDirectMembershipRule -CollectionId <String> -ResourceId <String> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDirectMembershipRule -CollectionId <String> [-ResourceName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDirectMembershipRule -CollectionName <String> [-ResourceName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDirectMembershipRule -CollectionName <String> -Resource <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDirectMembershipRule -CollectionName <String> -ResourceId <String> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDirectMembershipRule -InputObject <IResultObject> -Resource <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDirectMembershipRule -InputObject <IResultObject> -ResourceId <String> [<CommonParameters>]
```
```PowerShell
Get-CMCollectionDirectMembershipRule -InputObject <IResultObject> [-ResourceName <String>] [<CommonParameters>]
```
