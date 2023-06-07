Get-CMDeviceCollectionIncludeMembershipRule
-------------------------------------------




### Synopsis
Get an include membership rule for a device collection.



---


### Description

Use this cmdlet to get one or more include membership rules for a device collection. An include membership rule includes the members of another collection to the device collections where the rule is applied.



Configuration Manager dynamically updates the membership of the device collection on a schedule if the membership of the included collection changes.



For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Add-CMDeviceCollectionIncludeMembershipRule](Add-CMDeviceCollectionIncludeMembershipRule)



* [Remove-CMDeviceCollectionIncludeMembershipRule](Remove-CMDeviceCollectionIncludeMembershipRule)



* [Get-CMCollectionIncludeMembershipRule](Get-CMCollectionIncludeMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMUserCollectionIncludeMembershipRule](Get-CMUserCollectionIncludeMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Get all include membership rules
```PowerShell
Get-CMDeviceCollectionIncludeMembershipRule -CollectionName "Device"
```

#### Example 2: Get include membership rules by using the pipeline
```PowerShell
Get-CMCollection -Name "Device" | Get-CMDeviceCollectionIncludeMembershipRule
```



---


### Parameters
#### **CollectionId**

Specify the ID of the device collection to get the rule. This value is the CollectionID property, for example, `XYZ00012`. Since default collections don't have include membership rules, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the device collection to get the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **IncludeCollection**

Specify an object for the included collection to get the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **IncludeCollectionId**

Specify the ID of the included collection to get the rule. This value is the CollectionID property, for example, `XYZ00012`. You can include default collections, so this value can start with either the site code or `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **IncludeCollectionName**

Specify the name of the included collection to get the rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InputObject**

Specify an object for the device collection to get the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|





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
Get-CMDeviceCollectionIncludeMembershipRule -CollectionId <String> -IncludeCollection <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionIncludeMembershipRule -CollectionId <String> -IncludeCollectionId <String> [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionIncludeMembershipRule -CollectionId <String> [-IncludeCollectionName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionIncludeMembershipRule -CollectionName <String> [-IncludeCollectionName <String>] [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionIncludeMembershipRule -CollectionName <String> -IncludeCollection <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionIncludeMembershipRule -CollectionName <String> -IncludeCollectionId <String> [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionIncludeMembershipRule -IncludeCollection <IResultObject> -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionIncludeMembershipRule -IncludeCollectionId <String> -InputObject <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMDeviceCollectionIncludeMembershipRule [-IncludeCollectionName <String>] -InputObject <IResultObject> [<CommonParameters>]
```
