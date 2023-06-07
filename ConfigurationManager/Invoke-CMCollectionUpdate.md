Invoke-CMCollectionUpdate
-------------------------




### Synopsis
Update the membership of a collection.



---


### Description

Use this cmdlet to update the membership of a collection. The site evaluates the membership for the selected collection based on the collection's membership rules. For collections with many members, this update might take some time to finish.



For more information, see Collection evaluation in Configuration Manager (/mem/configmgr/core/clients/manage/collections/collection-evaluation).



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



* [Get-CMDeviceCollection](Get-CMDeviceCollection)



* [Get-CMUserCollection](Get-CMUserCollection)



* [Introduction to collections in Configuration Manager](Introduction to collections in Configuration Manager)





---


### Examples
#### Example 1: Update the membership of a collection using the pipeline
```PowerShell
Get-CMCollection -Id XYZ00014 | Invoke-CMCollectionUpdate
```

#### Example 2: Update the membership of a collection by name
```PowerShell
Invoke-CMCollectionUpdate -Name "UserCol1"
```



---


### Parameters
#### **CollectionId**

Specify the ID of the collection to update. This value is the CollectionID property, for example, `XYZ00012` or `SMS00001`.






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

Specify a collection object to update. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specify the name of a collection to update.






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
Invoke-CMCollectionUpdate -CollectionId <String> [-DisableWildcardHandling] [-ForceWildcardHandling] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMCollectionUpdate [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Invoke-CMCollectionUpdate [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-Confirm] [-WhatIf] [<CommonParameters>]
```
