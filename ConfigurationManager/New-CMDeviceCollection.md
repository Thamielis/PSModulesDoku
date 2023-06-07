New-CMDeviceCollection
----------------------




### Synopsis
Create a device collection.



---


### Description

Use this cmdlet to create a device collection based on a specific limiting collection. The limiting collection determines which devices can be a member of the device collection that you create. For instance, when you use the All Systems collection as the limiting collection, the new collection can include any device in the Configuration Manager hierarchy.



You can then add devices to the collection with membership rules. To add members to the device collection, use one of the following membership rule cmdlets:



- Add-CMDeviceCollectionDirectMembershipRule (Add-CMDeviceCollectionDirectMembershipRule.md)- Add-CMDeviceCollectionExcludeMembershipRule (Add-CMDeviceCollectionExcludeMembershipRule.md)- Add-CMDeviceCollectionIncludeMembershipRule (Add-CMDeviceCollectionIncludeMembershipRule.md)- Add-CMDeviceCollectionQueryMembershipRule (Add-CMDeviceCollectionQueryMembershipRule.md)For more information, see How to create collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/create-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Set-CMCollection](Set-CMCollection)



* [Remove-CMCollection](Remove-CMCollection)



* [Invoke-CMCollectionUpdate](Invoke-CMCollectionUpdate)



* [New-CMUserCollection](New-CMUserCollection)



* [Introduction to collections in Configuration Manager](Introduction to collections in Configuration Manager)





---


### Examples
#### Example 1: Create a device collection
```PowerShell
New-CMDeviceCollection -Name "Windows 11" -LimitingCollectionName "All Systems"
```



---


### Parameters
#### **Comment**

Specify an optional comment to describe and identify this collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **InputObject**

Specify an object for the limiting collection. To get this object, use the Get-CMCollection (Get-CMCollection.md) or [Get-CMDeviceCollection](Get-CMDeviceCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases           |
|-----------------|--------|--------|--------------|------------------|
|`[IResultObject]`|true    |named   |True (ByValue)|LimitingCollection|



#### **LimitingCollectionId**

Specify the ID of the limiting collection. This value is the CollectionID property, for example, `XYZ00012` or `SMS00001`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **LimitingCollectionName**

Specify the name of the limiting collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **Name**

Specify the name for the new device collection.






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
New-CMDeviceCollection [-Comment <String>] -InputObject <IResultObject> -Name <String> [-RefreshSchedule <IResultObject>] [-RefreshType {None | Manual | Periodic | Continuous | Both}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMDeviceCollection [-Comment <String>] -LimitingCollectionId <String> -Name <String> [-RefreshSchedule <IResultObject>] [-RefreshType {None | Manual | Periodic | Continuous | Both}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
New-CMDeviceCollection [-Comment <String>] -LimitingCollectionName <String> -Name <String> [-RefreshSchedule <IResultObject>] [-RefreshType {None | Manual | Periodic | Continuous | Both}] [-Confirm] [-WhatIf] [<CommonParameters>]
```
