Remove-CMDeviceCollectionQueryMembershipRule
--------------------------------------------




### Synopsis
Remove a query membership rule from a device collection.



---


### Description

Use this cmdlet to remove a query membership rule from a device collection. A query rule lets you dynamically update the membership of a collection based on a query that is run on a schedule. You can't remove query rules from the default collections. Any collection that you target should have an ID that starts with the site code, not `SMS`. For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



When you remove a query membership rule from a collection, multiple resources may no longer be members of the collection. This action can cause any software or configuration deployment to not apply to the devices.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeviceCollectionQueryMembershipRule](Get-CMDeviceCollectionQueryMembershipRule)



* [Add-CMDeviceCollectionQueryMembershipRule](Add-CMDeviceCollectionQueryMembershipRule)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Remove-CMCollectionQueryMembershipRule](Remove-CMCollectionQueryMembershipRule)



* [Remove-CMUserCollectionQueryMembershipRule](Remove-CMUserCollectionQueryMembershipRule)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Remove the query membership rules for a device collection
```PowerShell
Remove-CMDeviceCollectionQueryMembershipRule -CollectionName "Windows 10 devices" -RuleName "TPM" -Force
```



---


### Parameters
#### **CollectionId**

Specify the ID of the device collection to remove the rule. This value is the CollectionID property, for example, `XYZ00012`. Since you can't remove the query rules from default collections, this ID starts with the site code and not `SMS`.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Id     |



#### **CollectionName**

Specify the name of the device collection to remove the rule.






|Type      |Required|Position|PipelineInput|Aliases|
|----------|--------|--------|-------------|-------|
|`[String]`|true    |named   |False        |Name   |



#### **Force**

Run the command without asking for confirmation.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify an object for the device collection to remove the rule. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **RuleName**

Specify the name of the query rule to remove from the collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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
Remove-CMDeviceCollectionQueryMembershipRule -CollectionId <String> [-Force] -RuleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeviceCollectionQueryMembershipRule -CollectionName <String> [-Force] -RuleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Remove-CMDeviceCollectionQueryMembershipRule [-Force] -InputObject <IResultObject> -RuleName <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
