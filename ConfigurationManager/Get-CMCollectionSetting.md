Get-CMCollectionSetting
-----------------------




### Synopsis
Get the settings for a collection.



---


### Description

Use this cmdlet to get the settings for a collection. These settings include properties for device variables, power management, and maintenance windows. In most instances, use the dedicated cmdlets for these properties, for example:



- Get-CMDeviceCollectionVariable (Get-CMDeviceCollectionVariable.md)- Set-CMCollectionPowerManagement (Set-CMCollectionPowerManagement.md)- Get-CMMaintenanceWindow (Get-CMMaintenanceWindow.md)> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMCollection](Copy-CMCollection)



* [Export-CMCollection](Export-CMCollection)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMCollectionMember](Get-CMCollectionMember)



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
#### Example 1: Get the settings for a collection by using the pipeline
```PowerShell
Get-CMCollection -Id XYZ00014 | Get-CMCollectionSetting -CollectionType Device
```

#### Example 2: Get the settings for a collection by name
```PowerShell
Get-CMCollectionSetting -CollectionName "Devicecol1"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the collection to get its settings. This value is the CollectionID property, for example, `XYZ00012`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify the name of the collection to get its settings.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionType**

Filter the type of collection to get.



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



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**

Specify a collection object to get its settings. To get this object, use one of the following cmdlets:


* Get-CMCollection (Get-CMCollection.md)- Get-CMDeviceCollection (Get-CMDeviceCollection.md)- Get-CMUserCollection (Get-CMUserCollection.md)You can also use the pipeline operator (`|`) to pass a collection object to Get-CMCollectionMemeber on the command line.






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
Get-CMCollectionSetting -CollectionId <String> [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionSetting -CollectionName <String> [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ForceWildcardHandling] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionSetting [-CollectionType {User | Device}] [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [<CommonParameters>]
```
