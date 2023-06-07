Set-CMCollection
----------------




### Synopsis
Configure a device or user collection.



---


### Description

Use this cmdlet to configure a device or user collection.



The limiting collection determines which resources can be a member of the collection. For instance, when you use the All Systems collection as the limiting collection, the new collection can include any device in the Configuration Manager hierarchy.



Add resources to the collection with membership rules. To add members to the collection, use one of the cmdlets to add membership rules, for example:



- Add-CMDeviceCollectionQueryMembershipRule (Add-CMDeviceCollectionQueryMembershipRule.md)- Add-CMUserCollectionQueryMembershipRule (Add-CMUserCollectionQueryMembershipRule.md)You can't configure default collections. Any collection that you target should have an ID that starts with the site code, not `SMS`.



For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMCollection](Copy-CMCollection)



* [Export-CMCollection](Export-CMCollection)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMCollectionMember](Get-CMCollectionMember)



* [Get-CMCollectionSetting](Get-CMCollectionSetting)



* [Import-CMCollection](Import-CMCollection)



* [Invoke-CMCollectionUpdate](Invoke-CMCollectionUpdate)



* [New-CMCollection](New-CMCollection)



* [Remove-CMCollection](Remove-CMCollection)



* [Set-CMCollection](Set-CMCollection)



* [Set-CMDeviceCollectionVariable](Set-CMDeviceCollectionVariable)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Rename a collection
```PowerShell
$userCollection = Get-CMCollection -Name "testUser"
Set-CMCollection -InputObject $userCollection -NewName "newTestUser"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the collection to configure. This value is the CollectionID property, for example, `XYZ00012`. You can't configure default collections, so this value starts with the site code, not `SMS`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Comment**

Specify an optional comment to describe and identify this collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



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

Specify a collection object to configure. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **LimitingCollection**

Specify an object for the limiting collection. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **LimitingCollectionId**

Specify the ID of the limiting collection. This value is the CollectionID property, for example, `XYZ00012` or `SMS00001`.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|false   |named   |False        |LimitToCollectionId|



#### **LimitingCollectionName**

Specify the name of the limiting collection.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|false   |named   |False        |LimitToCollectionName|



#### **Name**

Specify the name of a collection to configure.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **NewName**

Specify a new name for the collection. Use this parameter to rename it.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RefreshSchedule**

If you set the RefreshType parameter to either `Periodic` or `Both`, use this parameter to set the schedule. Specify a schedule object for when the site runs a full update of the collection membership. To get this object, use the New-CMSchedule (New-CMSchedule.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|false   |named   |False        |



#### **RefreshType**

Specify how the collection membership is updated:


* `Manual` (1): An administrator manually triggers a membership update in the Configuration Manager console or with the Invoke-CMCollectionUpdate (Invoke-CMCollectionUpdate.md)cmdlet. - `Periodic` (2): The site does a full update on a schedule. It doesn't use incremental updates. If you don't specify a type, this value is the default.


* `Continuous` (4): The site periodically evaluates new resources and then adds new members. This type is also known as an incremental update . It doesn't do a full update on a schedule. - `Both` (6): A combination of both `Periodic` and `Continuous`, with both incremental updates and a full update on a schedule.


If you specify either `Periodic` or `Both`, use the RefreshSchedule parameter to set the schedule.


> [!NOTE] > The `None` value (0) is functionally the same as `Manual`.



Valid Values:

* None
* Manual
* Periodic
* Continuous
* Both






|Type                     |Required|Position|PipelineInput|
|-------------------------|--------|--------|-------------|
|`[CollectionRefreshType]`|false   |named   |False        |



#### **VariablePriority**

Specify an integer value from 1-9 for the priority of device collection variables. `1` is the lowest priority, and `9` is the highest.


To configure variables on a device collection, use the Set-CMDeviceCollectionVariable (Set-CMDeviceCollectionVariable.md)cmdlet.


To view the current variable priority, use the Get-CMCollectionSetting (Get-CMCollectionSetting.md)cmdlet.






|Type     |Required|Position|PipelineInput|Aliases                           |
|---------|--------|--------|-------------|----------------------------------|
|`[Int32]`|false   |named   |False        |DeviceCollectionVariablePrecedence|



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
Set-CMCollection -CollectionId <String> [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-LimitingCollection <IResultObject>] [-LimitingCollectionId <String>] [-LimitingCollectionName <String>] [-NewName <String>] [-PassThru] [-RefreshSchedule <IResultObject>] [-RefreshType {None | Manual | Periodic | Continuous | Both}] [-VariablePriority <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollection [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-LimitingCollection <IResultObject>] [-LimitingCollectionId <String>] [-LimitingCollectionName <String>] [-NewName <String>] [-PassThru] [-RefreshSchedule <IResultObject>] [-RefreshType {None | Manual | Periodic | Continuous | Both}] [-VariablePriority <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMCollection [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] [-LimitingCollection <IResultObject>] [-LimitingCollectionId <String>] [-LimitingCollectionName <String>] -Name <String> [-NewName <String>] [-PassThru] [-RefreshSchedule <IResultObject>] [-RefreshType {None | Manual | Periodic | Continuous | Both}] [-VariablePriority <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
