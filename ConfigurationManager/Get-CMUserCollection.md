Get-CMUserCollection
--------------------




### Synopsis
Get one or more user collections.



---


### Description

Use this cmdlet to get one or more user collections. To get either device or user collections, use the Get-CMCollection (Get-CMCollection.md)cmdlet. For more information about collections, see Introduction to Collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/introduction-to-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [New-CMUserCollection](New-CMUserCollection)



* [Remove-CMCollection](Remove-CMCollection)



* [Set-CMCollection](Set-CMCollection)



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Introduction to Collections in Configuration Manager](Introduction to Collections in Configuration Manager)





---


### Examples
#### Example 1: Get a user collection
```PowerShell
Get-CMUserCollection -CollectionId "SMS00002"
```



---


### Parameters
#### **DistributionPointGroup**

Specify a distribution point group object that's associated with this collection. To get this object, use the Get-CMDistributionPointGroup (Get-CMDistributionPointGroup.md)cmdlet.






|Type             |Required|Position|PipelineInput|
|-----------------|--------|--------|-------------|
|`[IResultObject]`|true    |named   |False        |



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



#### **Id**

Specify the ID of the user collection to get. This value is the CollectionID property, for example, `XYZ00013` or `SMS00002`.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CollectionId|



#### **Name**

Specify the name of the user collection to get.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |





---


### Inputs
None





---


### Outputs
* [Object](https://learn.microsoft.com/en-us/dotnet/api/System.Object)






---


### Notes
For more information on this return object and its properties, see SMS_Collection server WMI class (/mem/configmgr/develop/reference/core/clients/collections/sms_collection-server-wmi-class).



---


### Syntax
```PowerShell
Get-CMUserCollection -DistributionPointGroup <IResultObject> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollection -DistributionPointGroupId <String> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollection -DistributionPointGroupName <String> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollection -Id <String> [<CommonParameters>]
```
```PowerShell
Get-CMUserCollection [-Name <String>] [<CommonParameters>]
```
