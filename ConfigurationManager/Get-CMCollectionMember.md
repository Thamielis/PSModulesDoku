Get-CMCollectionMember
----------------------




### Synopsis
Get members of a device or user collection.



---


### Description

Use this cmdlet to get members of a collection. Collections can include devices or users, but not both. When you query a collection, this cmdlet returns objects for all members.



For more information, see Introduction to collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/introduction-to-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Copy-CMCollection](Copy-CMCollection)



* [Export-CMCollection](Export-CMCollection)



* [Get-CMCollection](Get-CMCollection)



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
#### Example 1: Get a member of a collection by using the pipeline operator
```PowerShell
Get-CMCollection -Name "UserCol1" | Get-CMCollectionMember | Select-Object Name
```

#### Example 2: Get a member of a collection by name
```PowerShell
Get-CMCollectionMember -CollectionName "DeviceCol1" -Name "domain*"
```

#### Example 3: Export collection details to a CSV
```PowerShell
$collMem = Get-CMCollectionMember -CollectionId "XYZ0004B" | Select-Object Name,Domain,LastLogonUser,DeviceOS,DeviceOSBuild,MACAddress,SerialNumber
$collMem | ConvertTo-Csv -NoTypeInformation | Out-File -FilePath "C:\output\XYZ0004B.csv"
```



---


### Parameters
#### **CollectionId**

Specify the ID of a collection to query. For example, `"XYZ0004B"`.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **CollectionName**

Specify the name of a collection to query.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



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

Specify a collection object to query. To get a collection object, use one of the following cmdlets:


* Get-CMCollection (Get-CMCollection.md)- Get-CMDeviceCollection (Get-CMDeviceCollection.md)- Get-CMUserCollection (Get-CMUserCollection.md)You can also use the pipeline operator (`|`) to pass a collection object to Get-CMCollectionMemeber on the command line.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **Name**

To filter the results, specify the name of a resource in the collection. This filter isn't case-sensitive.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|false   |named   |False        |ResourceName|



#### **ResourceId**

To filter the results, specify a resource ID. For example, `16777242`. The cmdlet only returns a record for that resource in the targeted collection.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **SmsId**

To filter the results, specify the SMSID of a resource. For example, `"GUID:7a186367-7372-4841-889e-ba2e3aad1e85"`. This filter isn't case-sensitive.


You can use wildcard characters:


* `*`: Multiple characters


* `?`: Single character






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




---


### Syntax
```PowerShell
Get-CMCollectionMember -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-ResourceId <Int32>] [-SmsId <String>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionMember -CollectionName <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Name <String>] [-ResourceId <Int32>] [-SmsId <String>] [<CommonParameters>]
```
```PowerShell
Get-CMCollectionMember [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Name <String>] [-ResourceId <Int32>] [-SmsId <String>] [<CommonParameters>]
```
