Set-CMSoftwareInventory
-----------------------




### Synopsis
Modifies an object that collects software inventory data on files.



---


### Description

The Set-CMSoftwareInventory cmdlet modifies an object that collects information about files on client devices in Configuration Manager.



> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Related Links
* [Get-CMSoftwareInventory](Get-CMSoftwareInventory)



* [Undo-CMSoftwareInventory](Undo-CMSoftwareInventory)





---


### Examples
#### Example 1: Set a software inventory object
```PowerShell
PS XYZ:\> Set-CMSoftwareInventory -Name "MSXML 6.0 Parser"
```
This command starts collecting software inventory data on the file named MSXML 6.0 Parser.


---


### Parameters
#### **CategoryId**

{{ Fill CategoryId Description }}






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **CleanTag1**

{{ Fill CleanTag1 Description }}






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|false   |named   |False        |CleanLabel1|



#### **CleanTag2**

{{ Fill CleanTag2 Description }}






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|false   |named   |False        |CleanLabel2|



#### **CleanTag3**

{{ Fill CleanTag3 Description }}






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[Switch]`|false   |named   |False        |CleanLabel3|



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **FamilyId**

Specifies the ID of the family used to classify inventoried software in Configuration Manager.






|Type     |Required|Position|PipelineInput|
|---------|--------|--------|-------------|
|`[Int32]`|false   |named   |False        |



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Id**

Specifies an array of IDs of software files.






|Type      |Required|Position|PipelineInput|Aliases    |
|----------|--------|--------|-------------|-----------|
|`[String]`|true    |named   |False        |SoftwareKey|



#### **InputObject**

Specifies a CMSoftwareInventory object. To obtain a CMSoftwareInventory object, use the Get-CMSoftwareInventory (Get-CMSoftwareInventory.md)cmdlet.






|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**

Specifies an array of names of software files.






|Type        |Required|Position|PipelineInput|Aliases   |
|------------|--------|--------|-------------|----------|
|`[String[]]`|true    |named   |False        |CommonName|



#### **NewName**

Specifies a new name for inventoried software in Configuration Manager.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **ParentSoftwareId**

{{ Fill ParentSoftwareId Description }}






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|false   |named   |False        |



#### **PassThru**

Add this parameter to return an object that represents the item with which you're working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Publisher**

Specifies the name of a software publisher in Configuration Manager.






|Type      |Required|Position|PipelineInput|Aliases        |
|----------|--------|--------|-------------|---------------|
|`[String]`|false   |named   |False        |CommonPublisher|



#### **Tag1Id**

Specifies the ID of a tag to classify inventoried software in Configuration Manager.






|Type     |Required|Position|PipelineInput|Aliases |
|---------|--------|--------|-------------|--------|
|`[Int32]`|false   |named   |False        |Label1Id|



#### **Tag2Id**

Specifies the ID of a tag to classify inventoried software in Configuration Manager.






|Type     |Required|Position|PipelineInput|Aliases |
|---------|--------|--------|-------------|--------|
|`[Int32]`|false   |named   |False        |Label2Id|



#### **Tag3Id**

Specifies the ID of a tag to classify inventoried software in Configuration Manager.






|Type     |Required|Position|PipelineInput|Aliases |
|---------|--------|--------|-------------|--------|
|`[Int32]`|false   |named   |False        |Label3Id|



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
Set-CMSoftwareInventory [-CategoryId <Int32>] [-CleanTag1] [-CleanTag2] [-CleanTag3] [-DisableWildcardHandling] [-FamilyId <Int32>] [-ForceWildcardHandling] -Id <String> [-NewName <String>] [-ParentSoftwareId <String>] [-PassThru] [-Publisher <String>] [-Tag1Id <Int32>] [-Tag2Id <Int32>] [-Tag3Id <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareInventory [-CategoryId <Int32>] [-CleanTag1] [-CleanTag2] [-CleanTag3] [-DisableWildcardHandling] [-FamilyId <Int32>] [-ForceWildcardHandling] -InputObject <IResultObject> [-NewName <String>] [-ParentSoftwareId <String>] [-PassThru] [-Publisher <String>] [-Tag1Id <Int32>] [-Tag2Id <Int32>] [-Tag3Id <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMSoftwareInventory [-CategoryId <Int32>] [-CleanTag1] [-CleanTag2] [-CleanTag3] [-DisableWildcardHandling] [-FamilyId <Int32>] [-ForceWildcardHandling] -Name <String[]> [-NewName <String>] [-ParentSoftwareId <String>] [-PassThru] [-Publisher <String>] [-Tag1Id <Int32>] [-Tag2Id <Int32>] [-Tag3Id <Int32>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
