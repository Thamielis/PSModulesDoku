New-CMCollection
----------------




### Synopsis
Create a device or user collection.



---


### Description

Use this cmdlet to create a device or user collection.



The limiting collection determines which resources can be a member of the collection that you create. For instance, when you use the All Systems collection as the limiting collection, since it's a device collection, the new device collection can include any device in the Configuration Manager hierarchy.



To scope the type of collection that you create, you can also use the New-CMDeviceCollection (New-CMDeviceCollection.md) or [New-CMUserCollection](New-CMUserCollection.md)cmdlets.



After you create a collection, add resources to the collection with membership rules. To add members to the collection, use one of the cmdlets to add membership rules, for example:



- Add-CMDeviceCollectionQueryMembershipRule (Add-CMDeviceCollectionQueryMembershipRule.md)- Add-CMUserCollectionQueryMembershipRule (Add-CMUserCollectionQueryMembershipRule.md)For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



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



* [Remove-CMCollection](Remove-CMCollection)



* [Set-CMCollection](Set-CMCollection)



* [New-CMDeviceCollectionVariable](New-CMDeviceCollectionVariable)



* [New-CMDeviceCollection](New-CMDeviceCollection)



* [New-CMUserCollection](New-CMUserCollection)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1: Create a user collection
```PowerShell
New-CMCollection -CollectionType User -LimitingCollectionName "All Users" -Name "testUser"
```

#### Example 2: Set the limiting collection through the pipeline
```PowerShell
Get-CMCollection -Name "All Users" | New-CMCollection -Name "testUser" -CollectionType "User"
```



---


### Parameters
#### **CollectionType**

Specify the type of collection to create. This parameter is functionally the same as using the New-CMDeviceCollection (New-CMDeviceCollection.md) or [New-CMUserCollection](New-CMUserCollection.md)cmdlets.



Valid Values:

* Root
* User
* Device
* Unknown






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[CollectionType]`|true    |named   |False        |



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

Specify an object for the limiting collection. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases           |
|-----------------|--------|--------|--------------|------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|LimitingCollection|



#### **LimitingCollectionId**

Specify the ID of the limiting collection. This value is the CollectionID property, for example, `XYZ00012` or `SMS00001`.






|Type      |Required|Position|PipelineInput|Aliases            |
|----------|--------|--------|-------------|-------------------|
|`[String]`|true    |named   |False        |LimitToCollectionId|



#### **LimitingCollectionName**

Specify the name of the limiting collection.






|Type      |Required|Position|PipelineInput|Aliases              |
|----------|--------|--------|-------------|---------------------|
|`[String]`|true    |named   |False        |LimitToCollectionName|



#### **Name**

Specify the name for the new collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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


To create variables on a device collection, use the New-CMDeviceCollectionVariable (New-CMDeviceCollectionVariable.md)cmdlet.






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
* IResultObject#SMS_Collection






---


### Notes
For more information on this return object and its properties, see SMS_Collection server WMI class (/mem/configmgr/develop/reference/core/clients/collections/sms_collection-server-wmi-class).



---


### Syntax
```PowerShell
New-CMCollection -CollectionType {User | Device} [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> -Name <String> [-RefreshSchedule <IResultObject>] [-RefreshType {None | Manual | Periodic | Continuous | Both}] [-VariablePriority <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMCollection -CollectionType {User | Device} [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -LimitingCollectionId <String> -Name <String> [-RefreshSchedule <IResultObject>] [-RefreshType {None | Manual | Periodic | Continuous | Both}] [-VariablePriority <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMCollection -CollectionType {User | Device} [-Comment <String>] [-DisableWildcardHandling] [-ForceWildcardHandling] -LimitingCollectionName <String> -Name <String> [-RefreshSchedule <IResultObject>] [-RefreshType {None | Manual | Periodic | Continuous | Both}] [-VariablePriority <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
