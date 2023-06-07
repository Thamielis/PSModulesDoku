Set-CMClientSettingSoftwareInventory
------------------------------------




### Synopsis
Sets a client setting software inventory.



---


### Description

> [!NOTE] > Run Configuration Manager cmdlets from the Configuration Manager site drive, for example `PS XYZ:>`. For more information, see getting started (/powershell/sccm/overview).



---


### Examples
#### Example 1
```PowerShell
PS XYZ:\>$inventoryFileTypeTable = @{FileName="*.exe";ExcludeWindirAndSubfolders=$True;ExcludeEncryptedAndCompressedFiles=$True;Subdirectories=$True;Path='All client hard disks'}
PS XYZ:\>$schedule = New-CMSchedule -Start '2022-01-01 04:00' -DayOfWeek Sunday -WeekOrder First
PS XYZ:\>Set-CMClientSettingSoftwareInventory -Name 'My custom setting' -Enable $true -Schedule $schedule -AddInventoryFileType $inventoryFileTypeTable
```



---


### Parameters
#### **AddCollectFile**








|Type           |Required|Position|PipelineInput|Aliases        |
|---------------|--------|--------|-------------|---------------|
|`[Hashtable[]]`|false   |named   |False        |AddCollectFiles|



#### **AddInventoryFileType**








|Type           |Required|Position|PipelineInput|Aliases              |
|---------------|--------|--------|-------------|---------------------|
|`[Hashtable[]]`|false   |named   |False        |AddInventoryFileTypes|



#### **CleanCollectFile**








|Type      |Required|Position|PipelineInput|Aliases          |
|----------|--------|--------|-------------|-----------------|
|`[Switch]`|false   |named   |False        |CleanCollectFiles|



#### **CleanInventoryFileType**








|Type      |Required|Position|PipelineInput|Aliases                |
|----------|--------|--------|-------------|-----------------------|
|`[Switch]`|false   |named   |False        |CleanInventoryFileTypes|



#### **DefaultSetting**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|true    |named   |False        |



#### **DisableWildcardHandling**

This parameter treats wildcard characters as literal character values. You can't combine it with ForceWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **Enable**








|Type       |Required|Position|PipelineInput|Aliases                |
|-----------|--------|--------|-------------|-----------------------|
|`[Boolean]`|false   |named   |False        |EnableSoftwareInventory|



#### **FileDisplayName**








|Type      |Required|Position|PipelineInput|Aliases                         |
|----------|--------|--------|-------------|--------------------------------|
|`[String]`|false   |named   |False        |SoftwareInventoryFileDisplayName|



#### **FileInventoriedName**








|Type      |Required|Position|PipelineInput|Aliases                             |
|----------|--------|--------|-------------|------------------------------------|
|`[String]`|false   |named   |False        |SoftwareInventoryFileInventoriedName|



#### **FileName**








|Type      |Required|Position|PipelineInput|Aliases                  |
|----------|--------|--------|-------------|-------------------------|
|`[String]`|false   |named   |False        |SoftwareInventoryFileName|



#### **ForceWildcardHandling**

This parameter processes wildcard characters and may lead to unexpected behavior (not recommended). You can't combine it with DisableWildcardHandling .






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **InputObject**








|Type             |Required|Position|PipelineInput |
|-----------------|--------|--------|--------------|
|`[IResultObject]`|true    |named   |True (ByValue)|



#### **Name**








|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[String]`|true    |named   |False        |



#### **PassThru**

Returns an object representing the item with which you are working. By default, this cmdlet may not generate any output.






|Type      |Required|Position|PipelineInput|
|----------|--------|--------|-------------|
|`[Switch]`|false   |named   |False        |



#### **RemoveCollectFile**








|Type           |Required|Position|PipelineInput|Aliases           |
|---------------|--------|--------|-------------|------------------|
|`[Hashtable[]]`|false   |named   |False        |RemoveCollectFiles|



#### **RemoveInventoryFileType**








|Type           |Required|Position|PipelineInput|Aliases                 |
|---------------|--------|--------|-------------|------------------------|
|`[Hashtable[]]`|false   |named   |False        |RemoveInventoryFileTypes|



#### **ReportOption**





Valid Values:

* None
* ProductOnly
* FileOnly
* FullDetail






|Type                |Required|Position|PipelineInput|
|--------------------|--------|--------|-------------|
|`[ReportOptionType]`|false   |named   |False        |



#### **Schedule**








|Type             |Required|Position|PipelineInput|Aliases                                        |
|-----------------|--------|--------|-------------|-----------------------------------------------|
|`[IResultObject]`|false   |named   |False        |InventorySchedule<br/>SoftwareInventorySchedule|



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
Set-CMClientSettingSoftwareInventory [-AddCollectFile <Hashtable[]>] [-AddInventoryFileType <Hashtable[]>] [-CleanCollectFile] [-CleanInventoryFileType] -DefaultSetting [-DisableWildcardHandling] [-Enable <Boolean>] [-FileDisplayName <String>] [-FileInventoriedName <String>] [-FileName <String>] [-ForceWildcardHandling] [-PassThru] [-RemoveCollectFile <Hashtable[]>] [-RemoveInventoryFileType <Hashtable[]>] [-ReportOption {None | ProductOnly | FileOnly | FullDetail}] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingSoftwareInventory [-AddCollectFile <Hashtable[]>] [-AddInventoryFileType <Hashtable[]>] [-CleanCollectFile] [-CleanInventoryFileType] [-DisableWildcardHandling] [-Enable <Boolean>] [-FileDisplayName <String>] [-FileInventoriedName <String>] [-FileName <String>] [-ForceWildcardHandling] -InputObject <IResultObject> [-PassThru] [-RemoveCollectFile <Hashtable[]>] [-RemoveInventoryFileType <Hashtable[]>] [-ReportOption {None | ProductOnly | FileOnly | FullDetail}] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
```PowerShell
Set-CMClientSettingSoftwareInventory [-AddCollectFile <Hashtable[]>] [-AddInventoryFileType <Hashtable[]>] [-CleanCollectFile] [-CleanInventoryFileType] [-DisableWildcardHandling] [-Enable <Boolean>] [-FileDisplayName <String>] [-FileInventoriedName <String>] [-FileName <String>] [-ForceWildcardHandling] -Name <String> [-PassThru] [-RemoveCollectFile <Hashtable[]>] [-RemoveInventoryFileType <Hashtable[]>] [-ReportOption {None | ProductOnly | FileOnly | FullDetail}] [-Schedule <IResultObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```
