Copy-CMCollection
-----------------




### Synopsis
Copy a collection to a new one.



---


### Description

Use this cmdlet to clone an existing collection to a new copy.



For more information, see How to manage collections in Configuration Manager (/mem/configmgr/core/clients/manage/collections/manage-collections).



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Export-CMCollection](Export-CMCollection)



* [Get-CMCollection](Get-CMCollection)



* [Get-CMCollectionMember](Get-CMCollectionMember)



* [Get-CMCollectionSetting](Get-CMCollectionSetting)



* [Import-CMCollection](Import-CMCollection)



* [Invoke-CMCollectionUpdate](Invoke-CMCollectionUpdate)



* [New-CMCollection](New-CMCollection)



* [Remove-CMCollection](Remove-CMCollection)



* [Set-CMCollection](Set-CMCollection)



* [How to create collections in Configuration Manager](How to create collections in Configuration Manager)





---


### Examples
#### Example 1
```PowerShell
Copy-CMCollection -Name "testUser" -NewName "testUserNew"
```
This command exports the collection named testUser to a new collection named testUserNew.


---


### Parameters
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



#### **Id**

Specify the ID of a collection to copy. This value is the CollectionID property, for example, `XYZ00012`.






|Type      |Required|Position|PipelineInput|Aliases     |
|----------|--------|--------|-------------|------------|
|`[String]`|true    |named   |False        |CollectionId|



#### **InputObject**

Specify a collection object to copy. To get this object, use the Get-CMCollection (Get-CMCollection.md), [Get-CMDeviceCollection](Get-CMDeviceCollection.md), or [Get-CMUserCollection](Get-CMUserCollection.md)cmdlets.






|Type             |Required|Position|PipelineInput |Aliases   |
|-----------------|--------|--------|--------------|----------|
|`[IResultObject]`|true    |named   |True (ByValue)|Collection|



#### **Name**

Specify the name of a collection to copy.






|Type      |Required|Position|PipelineInput|Aliases       |
|----------|--------|--------|-------------|--------------|
|`[String]`|true    |named   |False        |CollectionName|



#### **NewName**

Specify the name of the new collection.






|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[String]`|false   |named   |False        |NewCollectionName|



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






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
* IResultObject[]#SMS_Collection


* IResultObject#SMS_Collection






---


### Notes
For more information on this return object and its properties, see SMS_Collection server WMI class (/mem/configmgr/develop/reference/core/clients/collections/sms_collectionsettings-server-wmi-class).



---


### Syntax
```PowerShell
Copy-CMCollection [-DisableWildcardHandling] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Copy-CMCollection [-DisableWildcardHandling] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Copy-CMCollection [-DisableWildcardHandling] [-ForceWildcardHandling] -Name <String> [-NewName <String>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```
