Get-CMCollection
----------------




### Synopsis
Get a device or user collection object.



---


### Description

Use this cmdlet to get a device or user collection object.



Collections help you organize resources into manageable units. You can create collections to match your client management needs, and to perform operations on multiple resources at one time. Most management tasks rely on or require using one or more collections.



To scope the type of collection that you get, use the Get-CMDeviceCollection (Get-CMDeviceCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.



If you don't specify a collection by name, ID or object, this cmdlet returns all collections.



For more information, see Introduction to collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/introduction-to-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMCollection](Copy-CMCollection)



* [Export-CMCollection](Export-CMCollection)



* [Get-CMCollectionMember](Get-CMCollectionMember)



* [Get-CMCollectionSetting](Get-CMCollectionSetting)



* [Import-CMCollection](Import-CMCollection)



* [Invoke-CMCollectionUpdate](Invoke-CMCollectionUpdate)



* [New-CMCollection](New-CMCollection)



* [Remove-CMCollection](Remove-CMCollection)



* [Set-CMCollection](Set-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Introduction to collections in Configuration Manager](Introduction to collections in Configuration Manager)





---


### Examples
#### Example 1: Get a collection by name
```PowerShell
Get-CMCollection -Name "testUser"
```

#### Example 2: Get a collection for a distribution point group
```PowerShell
Get-CMDistributionPointGroup -Name "dpg1" | Get-CMCollection
```
When you distribute content to these collections, the site automatically distributes to all current members of this distribution point group. For more information, see Manage distribution point groups (/mem/configmgr/core/servers/deploy/configure/install-and-configure-distribution-points#bkmk_manage).


---


### Parameters
#### **CollectionType**

Filter the type of collection to get. This parameter is functionally the same as using the Get-CMDeviceCollection (Get-CMDeviceCollection.md) or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.



Valid Values:

* Root
* User
* Device
* Unknown






|Type              |Required|Position|PipelineInput|
|------------------|--------|--------|-------------|
|`[CollectionType]`|false   |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **DistributionPointGroup**

Specify a distribution point group object that's associated with this collection. To get this object, use the Get-CMDistributionPointGroup (Get-CMDistributionPointGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **DistributionPointGroupId**

Specify the GUID for a distribution point group that's associated with this collection. This value is the GroupID property, which is a standard GUID surrounded by curly brackets, for example, `{537e6303-69eb-4104-bf7b-7baf43ce2352}`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **DistributionPointGroupName**

Specify the name of a distribution point group that's associated with this collection.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specify the ID of the collection to get. This value is the CollectionID property, for example, `XYZ00012` or `SMS00001`.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CollectionId|



#### **Name**

Specify the name of the collection to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
Microsoft.ConfigurationManagement.ManagementProvider.IResultObject





---


### Outputs
* IResultObject[]#SMS_Collection


* IResultObject#SMS_Collection






---


### Notes
For more information on this return object and its properties, see SMS_Collection server WMI class (/mem/configmgr/develop/reference/core/clients/collections/sms_collection-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMCollection [-CollectionType {User | Device}] [-DisableWildcardHandling] -DistributionPointGroup <IResultObject> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCollection [-CollectionType {User | Device}] [-DisableWildcardHandling] -DistributionPointGroupId <String> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCollection [-CollectionType {User | Device}] [-DisableWildcardHandling] -DistributionPointGroupName <String> [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCollection [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMCollection [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [<CommonParameters>]
```
