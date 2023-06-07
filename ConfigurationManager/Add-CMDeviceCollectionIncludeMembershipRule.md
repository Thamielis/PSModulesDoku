Add-CMDeviceCollectionIncludeMembershipRule
-------------------------------------------




### Synopsis
Add an include membership rule to a device collection.



---


### Description

Use this cmdlet to add an include membership rule to a device collection. An include membership rule includes the members of another collection to the device collection where the rule is applied.



You can't add membership rules to default collections. Any collection that you target should have an ID that starts with the site code, not `SMS`. You can include a default collection, so the ID of an included collection can start with `SMS`.



Configuration Manager dynamically updates the membership of the device collection on a schedule if the membership of the included collection changes.



When you add an include membership rule to a collection, resources may become members of the collection. This action can cause any software or configuration deployment to apply to devices in the included collection.



For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeviceCollectionIncludeMembershipRule](Get-CMDeviceCollectionIncludeMembershipRule)



* [Remove-CMDeviceCollectionIncludeMembershipRule](Remove-CMDeviceCollectionIncludeMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Add-CMUserCollectionIncludeMembershipRule](Add-CMUserCollectionIncludeMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Add an include membership rule
```PowerShell
Add-CMDeviceCollectionIncludeMembershipRule -CollectionName "Device" -IncludeCollectionName "All Systems"
```

#### Example 2: Add an include membership rule to a collection by using the pipeline
```PowerShell
Get-CMCollection -Name "Device" | Add-CMDeviceCollectionIncludeMembershipRule -IncludeCollectionName "All Systems"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the device collection to add the rule. This value is the CollectionID property, for example, `XYZ00012`. Since default collections don't have include membership rules, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the device collection to add the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **IncludeCollection**

Specify an object for the included collection to add to the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



#### **IncludeCollectionId**

Specify the ID of the included collection to add to the rule. This value is the CollectionID property, for example, `XYZ00012`. You can include default collections, so this value can start with either the site code or `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **IncludeCollectionName**

Specify the name of the included collection to add to the rule.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **InputObject**

Specify an object for the device collection to add the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






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
Add-CMDeviceCollectionIncludeMembershipRule -CollectionId <String> -IncludeCollection <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeviceCollectionIncludeMembershipRule -CollectionId <String> -IncludeCollectionId <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeviceCollectionIncludeMembershipRule -CollectionId <String> -IncludeCollectionName <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeviceCollectionIncludeMembershipRule -CollectionName <String> -IncludeCollectionName <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeviceCollectionIncludeMembershipRule -CollectionName <String> -IncludeCollection <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeviceCollectionIncludeMembershipRule -CollectionName <String> -IncludeCollectionId <String> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeviceCollectionIncludeMembershipRule -IncludeCollection <IResultObject> -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeviceCollectionIncludeMembershipRule -IncludeCollectionId <String> -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Add-CMDeviceCollectionIncludeMembershipRule -IncludeCollectionName <String> -InputObject <IResultObject> [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```